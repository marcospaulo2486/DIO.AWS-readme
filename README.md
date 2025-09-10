# DIO.AWS-readme
Projeto que idealiza uma implementação básica que visa reduzir custo de uma empresa fictícia com ferramentas AWS.

# RELATÓRIO DE IMPLEMENTAÇÃO AWS

Data: 09/09/25
Empresa: Abstergo Industries
Responsável: Marcos Paulo F. de Castro

## Introdução
Este relatório apresenta o processo de implementaçã de ferramentas na empresa Abstergo Industries, realizado por Marcos Paulo F Castro. O objetivo é elencar serviços AWS com a finalidade de realizar uma diminuição de custos imediatos.

## Descrição do Projeto  
O projeto de implementação de ferramentas foi dividido em etapas, cada uma com seus objetivos específicos:

### Etapa 1: Armazenamento;
- Ferramenta AWS: Amazon S3.

- Foco da Ferramenta: Armazenamento de objetos seguro, escalável e de alto desempenho, com classes de armazenamento para otimização automática de custos.

- Centralizar todo o armazenamento de dados da Abstergo no Amazon S3. Dados de pesquisa genética (PB-scale), resultados de testes clínicos e documentos regulatórios serão armazenados aqui. Para redução imediata de custos, implementaremos a classe S3 Intelligent-Tiering, que move automaticamente os dados entre tiers de acesso (frequente, infrequente e arquivo) baseado no padrão de uso, sem taxas de recuperação ou overhead de gestão. Dados que não são acessados há mais de 90 dias (como ensaios clínicos finalizados) serão automaticamente movidos para S3 Glacier Deep Archive, reduzindo o custo de armazenamento em mais de 75% comparado ao padrão.

### Etapa 2: Governança e dados sensíveis;
- Ferramenta AWS: AWS IAM (Identity and Access Management).

- Foco da Ferramenta: Controle centralizado de acesso seguro aos serviços e recursos da AWS, seguindo o princípio do menor privilégio.

- Descrição de Caso de Uso: Substituir credenciais de acesso genéricas por políticas granulares de IAM. Pesquisadores terão acesso apenas aos buckets e dados específicos de seus projetos no S3. O time de compliance terá acesso apenas a logs de auditoria. Integraremos o IAM com o Active Directory corporativo existente via AWS Directory Service, permitindo que os funcionários usem suas credenciais corporativas para login (SSO), aumentando a segurança e simplificando a gestão.

### Etapa 3: Monitoramento;
- Ferramenta AWS: Amazon CloudWatch.

- Foco da Ferramenta: Monitoramento de recursos e aplicações, coleta de logs e definição de alarmes.

- Descrição de Caso de Uso: Configurar o CloudWatch para monitorar a performance de todos os recursos AWS. Criaremos dashboards para visualizar em tempo real a latência de acesso aos dados no S3 e o uso de recursos. Alarmes serão configurados para notificar automaticamente a equipe de operações em caso de queda de performance ou indisponibilidade, permitindo uma resposta rápida para minimizar impactos nas operações de pesquisa.

## Conclusão
A sinergia técnica entre Amazon S3, AWS IAM e Amazon CloudWatch estabelece um modelo de custo operacional radicalmente eficiente, onde a despesa é estritamente proporcional ao uso real (pay-as-you-go). O S3 elimina o custo fixo do storage físico e introduz economias automáticas através de suas classes de armazenamento. O IAM reduz custos operacionais de gestão e mitiga riscos financeiros catastróficos associados a violações de dados. Por fim, o CloudWatch fornece os insights necessários para dirigir uma otimização contínua e garantir que a escalabilidade, que é um atributo intrínseco desta arquitetura, não comprometa a performance ou o controle financeiro. Juntos, esses serviços não apenas promovem uma redução de custos imediata e significativa, mas também transformam a infraestrutura de TI da Abstergo em um facilitador escalável e resiliente para inovação e crescimento.
