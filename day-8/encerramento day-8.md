Hoje o dia foi dedicado dois componentes importantes do Kubernetes: Secrets e ConfigMaps.

Secrets no Kubernetes são um recurso que nos permite gerenciar informações sensíveis, como senhas, tokens OAuth, chaves ssh, etc. Devido à sua natureza sensível, o Kubernetes oferece uma série de recursos para gerenciar Secrets de maneira segura. Usamos o recurso base64 para codificar nossas senhas e chaves secretas. Aprendemos como criar, obter e descrever um Secret, bem como como excluir um Secret.

Fomos além e usamos o Secret para armazenar um certificado TLS e uma chave privada, que usamos para configurar o Nginx para usar HTTPS. Usamos o Secret para montar o certificado TLS e a chave privada em um Pod do Nginx, e usamos um arquivo de manifesto para definir o Secret.

Depois disso, exploramos ConfigMaps. ConfigMaps são uma maneira eficiente de separar parâmetros de configuração de imagens de container, permitindo que você tenha a mesma imagem de container rodando em diferentes ambientes como desenvolvimento, teste e produção, mas com configurações diferentes.

Vimos:

Atualizar um ConfigMap.
Usar o ConfigMaps.
Usar o ConfigMap para definir variáveis de ambiente para os containers no Pod.
Tornar ConfigMaps imutáveis.
Criamos um arquivo de configuração do Nginx usando um ConfigMap, que usamos para configurar um Pod do Nginx. Também exploramos como montar o ConfigMap em um volume e como usar um arquivo de manifesto para definir o ConfigMap.
Finalmente, usamos o ConfigMap e o Secret juntos para configurar um Pod do Nginx para usar HTTPS, onde o ConfigMap é usado para armazenar o arquivo de configuração do Nginx e o Secret é usado para armazenar o certificado TLS e a chave privada.

Essa combinação de ConfigMaps e Secrets não só nos permite gerenciar nossas configurações e dados sensíveis de maneira eficiente e segura, mas também nos oferece um alto grau de flexibilidade e controle sobre as nossas aplicações.

E isso é tudo por hoje, chega! :D

Vejo você no próximo dia, até láááá!   👋   ✌️

