import streamlit as st
import numpy as np

# Coeficientes del modelo logístico sin interacción
b0 = -0.0457
b_ldl = -0.0131
b_estat = 0.0433

st.set_page_config(page_title="Calculadora de Riesgo LDL < 55")
st.title("Calculadora de Riesgo: LDL < 55 mg/dL")

st.markdown("Ingrese los datos del paciente para estimar la probabilidad de lograr LDL < 55.")

# Entrada del usuario
ldl = st.slider("LDL (mg/dL)", min_value=50, max_value=200, value=100)
estatinas = st.radio("¿El paciente está tomando estatinas?", [0, 1], format_func=lambda x: "Sí" if x else "No")

# Cálculo sin interacción
logit = b0 + b_ldl * ldl + b_estat * estatinas
prob = 1 / (1 + np.exp(-logit))

# Resultado
st.subheader("Resultado")
st.metric("Probabilidad estimada de LDL < 55", f"{prob*100:.1f}%")
