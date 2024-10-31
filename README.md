# mvp-datamesh-aws-

Estrutura de diretórios

https://chatgpt.com/share/6722fb8e-5dd4-8011-9843-c6d569de806c

# Estrutura de Diretórios
Este repositório foi organizado para manter uma separação clara entre o código-fonte, infraestrutura, dados e testes, facilitando a manutenção e expansão do projeto. Abaixo está uma descrição de cada diretório e sua função:

mvp-datamesh-aws/
├── src/
│   ├── data_catalog/
│   ├── glue_jobs/
│   ├── lake_formation/
│   ├── s3/
│   ├── iceberg/
│   └── utils/
├── tests/
├── infra/
│   └── modules/
├── data/
│   ├── raw/
│   ├── processed/
│   ├── transformed/
│   └── iceberg/
├── scripts/
├── requirements.txt
├── terraform.tfvars
├── .gitignore
└── README.md

## Descrição dos Diretórios
src/: Contém o código-fonte principal para todas as interações e operações no ambiente de DataMesh.

data_catalog/: Scripts e configurações para criação e gerenciamento de catálogos de dados usando o AWS Glue Data Catalog.
glue_jobs/: Contém os scripts ETL para execução no AWS Glue, incluindo operações de ingestão, transformação de dados e, futuramente, integração com Apache Iceberg.
lake_formation/: Scripts para gerenciamento de permissões e políticas no AWS Lake Formation.
s3/: Operações com Amazon S3, como a criação de buckets e o gerenciamento de arquivos de dados.
iceberg/: Scripts para operações e configurações específicas do Apache Iceberg, incluindo criação e versionamento de tabelas. Este módulo facilita o controle de versões e histórico dos dados nas camadas de armazenamento.
utils/: Contém funções utilitárias que são usadas em vários scripts para simplificar e padronizar o código.
tests/: Contém os testes automatizados para verificar a funcionalidade de cada módulo. Os testes são organizados para refletir a estrutura do diretório src/, permitindo testes direcionados para cada módulo individual. Moto e Pytest são usados para simulações e testes.

infra/: Diretório com os arquivos de configuração do Terraform, usados para provisionar a infraestrutura necessária na AWS.

modules/: Módulos de infraestrutura, que incluem configurações de recursos AWS reutilizáveis, como AWS Glue, Lake Formation e Apache Iceberg, organizados em módulos Terraform para fácil manutenção.
data/: Armazena dados simulados para desenvolvimento e testes locais.

raw/: Dados brutos que simulam o ambiente SOR (System of Record).
processed/: Dados processados para o ambiente SOT (System of Truth).
transformed/: Dados transformados prontos para consumo no ambiente SPEC (Serviço Específico ou Data Mart).
iceberg/: Contém os metadados e arquivos de versionamento para tabelas Iceberg, incluindo snapshots e manifestos que registram o histórico dos dados na camada SOR e, opcionalmente, na SOT.
scripts/: Scripts auxiliares para automação e configuração, como scripts de deploy e configuração de ambiente.

requirements.txt: Lista de dependências Python necessárias, incluindo Moto, Boto3, Pytest e outras.

Esta estrutura foi projetada para facilitar a expansão e manter uma abordagem modular, permitindo futuras adições, como o versionamento com Apache Iceberg, sem a necessidade de grandes reestruturações. Cada camada da arquitetura possui seu próprio espaço dedicado, o que ajuda a organizar melhor os dados e o código em um fluxo de ingestão, processamento e consumo eficiente.