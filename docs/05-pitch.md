# Pitch (3 minutos)



### 1. O Problema (30 seg)
> Qual dor do cliente você resolve?

No mercado financeiro, fundos de investimento precisam ter suas rentabilidades calculadas diariamente com alta precisão.
Erros operacionais podem acontecer nesse processo, gerando valores inconsistentes que podem impactar relatórios, cotas e decisões internas.
Hoje, essa validação muitas vezes é manual através de planilhas de Excel e sujeita a falhas humanas, o que aumenta o risco operacional.


### 2. A Solução (1 min)
> Como seu agente resolve esse problema?

Para resolver esse problema, desenvolvi a Analista AMC, uma agente inteligente focado em backoffice de fundos.
Ele analisa automaticamente a rentabilidade dos últimos dias, calcula uma banda de normalidade com base na média e desvio padrão, e identifica outliers.
Além disso, ele compara o comportamento do fundo com o IBOV, garantindo que a análise leve em consideração o movimento do mercado.
Quando identifica um desvio relevante que não acompanha o IBOV, o sistema sinaliza como possível erro operacional, permitindo que o analista reprocesse o fundo e corrija tal erro operacional.

### 3. Demonstração (1 min)
> Mostre o agente funcionando (pode ser gravação de tela)

Na demonstração, apresento a interface do sistema desenvolvida em Streamlit.
Mostro o carregamento dos dados do fundo e o cálculo automático da média e da banda de variação.
Em seguida, o sistema identifica um dia específico, 10 de março de 2026, onde a rentabilidade está fora da banda e não acompanha o IBOV, sinalizando um possível erro.
Também demonstro o chat com IA, onde o usuário pode perguntar sobre a análise, e o agente responde de forma controlada, sem sair do escopo operacional.


### 4. Diferencial e Impacto (30 seg)
> Por que essa solução é inovadora e qual é o impacto dela na sociedade?

O principal diferencial da solução é o uso de inteligência artificial alinhada a regras de negócio específicas do backoffice, evitando alucinações e respostas fora de contexto.
O impacto é a redução de risco operacional, aumento da eficiência na validação de fundos e maior confiabilidade nos dados financeiros.
Essa solução pode ser aplicada em bancos, gestoras e fintechs, contribuindo para processos mais seguros e automatizados no mercado financeiro.


Esse projeto demonstra como IA pode ser aplicada de forma prática e segura em processos críticos do mercado financeiro.

---

 Local URL: http://localhost:8501
Network URL: http://192.168.0.86:8501
