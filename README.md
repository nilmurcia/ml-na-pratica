# ml-na-pratica
Projeto DIO - Trabalhando com Machine Learning na Prática no Azure ML

# Passo 1: Criar uma conta no Azure
Acesse o site oficial do Microsoft Azure.
Faça login ou crie uma conta.
Ative o período gratuito, se aplicável, para obter créditos de avaliação.

#Passo 2: Criar um workspace no Azure Machine Learning
No portal do Azure, procure por "Machine Learning" na barra de pesquisa.
Clique em "Criar" e selecione "Workspace de Machine Learning".
Preencha os campos obrigatórios:
  - Grupo de Recursos: Escolha um existente ou crie um novo.
  - Nome do Workspace: Insira um nome único.
  - Região: Escolha a região mais próxima para reduzir a latência.
Clique em "Revisar + Criar" e, em seguida, em "Criar".

# Passo 3: Configurar o ambiente de desenvolvimento
  # Opção 1: Azure Machine Learning Studio
    Acesse o Azure Machine Learning Studio por meio do link fornecido após criar o workspace.
    Use a interface gráfica para gerenciar datasets, modelos e experimentos.
# Opção 2: Configurar localmente com o Azure CLI
  1. Instale o Azure CLI e o SDK do Azure Machine Learning:
      pip install azureml-sdk
  2. Faça login no Azure CLI:
      az login
  3. Conecte-se ao seu workspace:
     az ml workspace show -w <nome_do_workspace> -g <nome_do_grupo_de_recursos>

# Passo 4: Configurar um compute target
  1. No Azure Machine Learning Studio, vá para a aba "Compute".
  2. Escolha "Compute Instances" para criar um ambiente de desenvolvimento ou "Compute Clusters" para treinar modelos.
  3. Configure as especificações, como:
      Tipo de máquina virtual (e.g., Standard_DS11_v2).
      Autoescala (para clusters).

# Passo 5: Fazer upload de datasets
  1. No Azure Machine Learning Studio, vá para a aba "Datasets".
  2. Clique em "Criar Dataset" e selecione a origem (local ou URL).
  3. Configure as opções de pré-processamento e verifique os dados.

# Passo 6: Criar e treinar um modelo
# Opção 1: Usando Jupyter Notebooks
  1. No Azure Machine Learning Studio, vá para "Notebooks".
  2. Crie ou faça upload de um notebook Python.
  3. Configure o ambiente de execução:
      from azureml.core import Workspace, Experiment
      ws = Workspace.from_config()
      experiment = Experiment(workspace=ws, name='meu-experimento')

# Opção 2: Designer (Interface Gráfica)
  1. Vá para a aba "Designer".
  2. Arraste os componentes necessários, como datasets, algoritmos e saídas.
  3. Conecte os componentes e execute o pipeline.

# Passo 7: Implantar o modelo
  1. Vá para a aba "Modelos" no Machine Learning Studio.
  2. Clique em "Registrar Modelo".
  3. Configure um endpoint para disponibilizar o modelo por meio de API.
  4. Escolha o tipo de implantação (e.g., Kubernetes, Azure Container Instances).

# Passo 8: Monitorar e otimizar
  1. Use a aba "Monitoramento" no Azure Machine Learning Studio para acompanhar o desempenho dos experimentos.
  2. Ajuste os hiperparâmetros ou re-treine o modelo conforme necessário.
