---

copyright:

  years:  2016, 2018

lastupdated: "2018-09-21"

---

# Removendo o Hybridity Bundle de uma instância do vCenter Server

Para remover a licença do Hybridity Bundle de sua instância do vCenter Server, deve-se substituir as chaves de licença de aluguel do VMware NSX e VMware vSAN por chaves Bring Your Own License (BYOL) no VMware vSphere Web Client. Além disso, deve-se abrir um chamado de suporte para cancelar encargos das licenças de aluguel.

**Importante:** fazer downgrade de sua licença pode causar falha na instância do vCenter Server. É possível optar por fazer downgrade de uma licença por sua conta e risco, mas primeiro considere as funções que não estão disponíveis ao fazer o downgrade. Para obter mais informações, consulte [Gráfico de comparação para edições do componente VMware](../archiref/solution/appendix.html).

## Antes de remover o Hybridity Bundle

Verifique os requisitos a seguir antes de remover o Hybridity Bundle:

* Você tem uma instância do vCenter Server V2.4 ou mais recente com o Hybridity Bundle ativado.
* Você não tem o serviço VMware HCX on {{site.data.keyword.cloud_notm}} instalado em sua instância do vCenter Server.
* Você tem acesso ao VMware vSphere Web Client como Administrador.
* Se ainda não estiver aplicado, você terá as chaves de BYOL disponíveis para solicitar o VMware NSX e cada cluster VMware vSAN.
* Opcionalmente, e se ainda não estiver aplicado, você terá as chaves de BYOL disponíveis para solicitar as licenças do VMware vCenter Server e do VMware vSphere Enterprise Plus.

## Procedimento para remover o Hybridity Bundle

1. Efetue login no VMware vSphere Web Client como **Administrador**.
2. Clique em **Página inicial > Administração > Licenciamento > Licenças**.
3. Clique na guia **Ativos**.
4. Conclua as etapas a seguir para instalar um BYOL do VMware NSX:
   1. Clique na guia **Soluções**.
   2. Selecione NSX for vSphere e clique em **Todas as ações > Designar licença**.
   3. Clique no ícone **Incluir** e digite a chave de licença. Clique em **Avançar**.
   4. Digite o nome da licença e clique em **Avançar**. Clique em **Concluir** para incluir a licença.
   5. Selecione a nova chave de licença.
   6. Anote as chaves de licença completas da licença aplicada e da licença substituída. **Importante:** deve-se ter os detalhes da licença disponíveis para uso posterior neste procedimento.
   7. Clique em **OK** para designar a licença.
5. Conclua as etapas a seguir para instalar um BYOL do VMware vSAN:
   1. Clique na guia **Clusters**.
   2. Conclua as etapas a seguir para cada cluster vSAN associado à sua instância do vCenter Server:
    1. Selecione um cluster vSAN e clique em **Todas as ações > Designar licença**.
    2. Clique no ícone **Incluir** e digite a chave de licença. Clique em **Avançar**.
    3. Digite o nome da licença e clique em **Avançar**. Clique em **Concluir** para incluir a licença.
    4. Selecione a nova chave de licença.
    5. Anote o nome do cluster e as chaves de licença completas da licença que é aplicada e da licença que é substituída. **Importante:** deve-se ter os detalhes da licença disponíveis para uso posterior neste procedimento.
    6. Clique em **OK** para designar a licença.
6. Opcionalmente, conclua as etapas a seguir para instalar um BYOL do VMware vCenter Server:
   1. Clique na guia **Sistemas vCenter Server**.
   2. Selecione vCenter Server e clique em **Todas as ações > Designar licença**.
   3. Clique no ícone **Incluir** e digite a chave de licença. Clique em **Avançar**.
   4. Digite o nome da licença e clique em **Avançar**. Clique em **Concluir** para incluir a licença.
   5. Selecione a nova chave de licença.
   6. Anote as chaves de licença completas da licença aplicada e da licença substituída. **Importante:** deve-se ter os detalhes da licença disponíveis para uso posterior neste procedimento.
   7. Clique em **OK** para designar a licença.
7. Opcionalmente, conclua as etapas a seguir para instalar um BYOL do VMware vSphere Enterprise Plus:
  1. Clique na guia **Hosts**.
  2. Conclua as etapas a seguir para cada cluster associado à instância do vCenter Server ou conclua para todos os clusters ao mesmo tempo se a mesma licença estiver sendo aplicada a todos os clusters associados ao servidor vCenter:
    1. Selecione todos os hosts associados ao cluster e clique em **Todas as ações > Designar licença**.
    2. Clique no ícone **Incluir** e digite a chave de licença. Clique em **Avançar**.
    3. Digite o nome da licença e clique em **Avançar**. Clique em **Concluir** para incluir a licença.
    4. Selecione a nova chave de licença.
    5. Anote o nome do cluster e as chaves de licença completas da licença que é aplicada e da licença que é substituída. **Importante:** deve-se ter os detalhes da licença disponíveis para uso posterior neste procedimento. Se as chaves de licença não forem iguais em todos os clusters, assegure-se de anotar o nome do cluster associado a cada chave de licença.
    6. Clique em **OK** para designar a licença.
8. Remova as licenças de aluguel.
   1. Clique na guia **Licenças**.
   2. Selecione as licenças substituídas nas etapas 4 a 7.
   3. Clique no ícone **Remover licenças**.
9. Abra um chamado de suporte e forneça as seguintes informações para cancelar encargos das licenças de aluguel:
  * O nome de sua instância do vCenter Server.
  * O ID associado à instância do vCenter Server.
  * Uma lista das chaves de licença de BYOL instaladas neste procedimento. Quando aplicável, forneça o nome do cluster com chaves de licença para os clusters vSphere e vSAN.
  * Uma lista das chaves de licença de aluguel removidas neste procedimento. Quando aplicável, forneça o nome do cluster com chaves de licença para os clusters vSphere e vSAN.

  **Nota:** as equipes de Suporte e Operações da IBM acessam a camada de gerenciamento do vCenter de sua conta de infraestrutura do {{site.data.keyword.cloud_notm}} (SoftLayer) para verificar se as licenças de aluguel foram removidas antes de cancelar os encargos de licença de aluguel do Hybridity Bundle.

### Links relacionados

* [Pedindo instâncias do vCenter Server with Hybridity Bundle](vc_hybrid_orderinginstance.html)
* [Visualizando instâncias do vCenter Server with Hybridity Bundle](vc_hybrid_viewinginstances.html)
* [Entrando em contato com o Suporte IBM](../vmonic/trbl_support.html)