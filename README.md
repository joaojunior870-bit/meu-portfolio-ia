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









# PROJETO: Calculadora Inteligente de Tempo de Entrega
# OBJETIVO: Ajustar a expectativa do cliente baseado em clima e distância
# Foco: Logística e Operações

def calcular_tempo_estimado(distancia_km, esta_chovendo, transito_intenso):
    """
    Algoritmo que calcula o tempo de entrega considerando variáveis externas.
    """
    tempo_base = 10 # Tempo de preparo no restaurante (minutos)
    velocidade_media = 2 # minutos por km (moto)
    
    # Cálculo físico simples
    tempo_deslocamento = distancia_km * velocidade_media
    
    # Penalidades (Fatores de Risco)
    adicional_chuva = 0
    adicional_transito = 0
    
    if esta_chovendo:
        adicional_chuva = 15 # Motoboys pilotam mais devagar na chuva
        print("🌧️ Alerta: Chuva detectada! Adicionando margem de segurança.")
        
    if transito_intenso:
        adicional_transito = 20
        print("🚗 Alerta: Trânsito intenso na região.")

    tempo_total = tempo_base + tempo_deslocamento + adicional_chuva + adicional_transito
    return tempo_total

# --- SIMULAÇÃO ---
distancia = 8.5 # km
chuva = True
transito = False

tempo_final = calcular_tempo_estimado(distancia, chuva, transito)

print("-" * 30)
print(f"🛵 Distância: {distancia}km")
print(f"⏱️ Tempo Estimado de Entrega: {tempo_final} minutos")









# PROJETO: Sistema de Recomendação de Pratos (Simples)
# OBJETIVO: Sugerir comida baseada no perfil do cliente (Personalização)

def recomendar_prato(preferencia_usuario):
    # Base de Dados de Pratos (Simulada)
    cardapio = [
        {"prato": "Açaí com Granola", "categoria": "saudavel", "tempo": 15},
        {"prato": "X-Bacon Duplo", "categoria": "fast-food", "tempo": 30},
        {"prato": "Salada Caesar", "categoria": "saudavel", "tempo": 20},
        {"prato": "Pizza Calabresa", "categoria": "fast-food", "tempo": 45},
        {"prato": "Sushi Combo", "categoria": "japonesa", "tempo": 40}
    ]
    
    sugestoes = []
    
    print(f"🔎 Buscando opções para quem gosta de: {preferencia_usuario.upper()}...\n")
    
    for item in cardapio:
        # Lógica de Filtro (Content-Based Filtering)
        if item["categoria"] == preferencia_usuario:
            sugestoes.append(item)
            
    return sugestoes

# --- INTERFACE DO USUÁRIO ---
perfil_cliente = "saudavel" # Tente trocar por "fast-food" ou "japonesa"
resultados = recomendar_prato(perfil_cliente)

if len(resultados) > 0:
    print(f"✅ Encontramos {len(resultados)} opções perfeitas para você:")
    for opcao in resultados:
        print(f" - {opcao['prato']} (Chega em {opcao['tempo']} min)")
else:
    print("❌ Nenhuma opção encontrada nesta categoria.")
