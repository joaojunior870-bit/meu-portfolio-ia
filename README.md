# Portfólio de Candidatura | iFood GenAI 🚀🍕

Olá! Sou João de Deus, de Natal-RN.

Sou estudante com base em Biofísica/Ciência e estou transicionando para **Inteligência Artificial**.
Minha formação científica me ensinou a analisar padrões complexos, e quero aplicar esse rigor analítico para melhorar a experiência dos clientes no **iFood**.

### 💡 Sobre este Projeto
Criei este algoritmo em Python para demonstrar como a **IA Generativa** e o **Processamento de Linguagem Natural (NLP)** podem ser usados para:
1. Ler automaticamente comentários de pedidos.
2. Identificar palavras-chave (positivas ou negativas).
3. Classificar o "humor" do cliente para ajudar restaurantes a melhorarem.

---
**Tecnologias:** Python, Lógica de Algoritmos, Análise de Dados.

E-mail: joaojunior870@gmail.com







---

### 💻 MEU CÓDIGO (Simulação de IA para o iFood):

```python
# PROJETO: Analisador de Sentimento de Delivery (MVP)
# Foco: Customer Experience (CX)

def analisar_comentario_ifood(comentario):
    # Banco de Palavras-Chave (Simples)
    palavras_amor = ["rápido", "quentinha", "delícia", "ótimo", "amei"]
    palavras_dor = ["fria", "demorou", "atraso", "errado", "ruim"]
    
    texto = comentario.lower()
    score = 0
    motivos = []

    # Lógica de Classificação
    for palavra in palavras_amor:
        if palavra in texto:
            score += 1
            motivos.append(f"Positivo: {palavra}")
            
    for palavra in palavras_dor:
        if palavra in texto:
            score -= 1
            motivos.append(f"Negativo: {palavra}")

    # Decisão
    if score > 0:
        return "🌟 CLIENTE FELIZ", motivos
    elif score < 0:
        return "⚠️ CLIENTE INSATISFEITO", motivos
    else:
        return "😐 NEUTRO", motivos

# Teste Rápido
print(analisar_comentario_ifood("A pizza chegou fria e demorou"))
