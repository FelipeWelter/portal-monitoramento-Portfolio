# Portal de Monitoramento

O **Portal de Monitoramento** é um painel web para acompanhar a disponibilidade de serviços internos e consultar as principais métricas do servidor. Ele reúne, em uma única tela, o status dos serviços, os tempos de resposta e atalhos para os sistemas cadastrados.

<img width="1912" height="959" alt="Painel hospedado com status dos serviços, tempos de resposta e métricas do servidor" src="https://github.com/user-attachments/assets/b2ec619d-b43d-4d4f-b746-8f5975cd56c0" />

*Versão hospedada do Portal de Monitoramento em funcionamento.*

## O que o painel monitora

- **Conectividade por ping (ICMP).** Verifica se um equipamento responde pelo endereço IP ou nome de host e exibe a latência da resposta quando disponível.
- **Disponibilidade por HTTP/HTTPS.** Consulta aplicações web e exibe o status e o tempo de resposta da verificação.
- **Métricas do servidor.** Exibe uso de CPU, memória e disco, além do tempo de atividade.
- **Atualização automática.** Mantém os indicadores atualizados para ajudar a equipe de TI a identificar indisponibilidades e iniciar o diagnóstico.

O projeto foi desenvolvido em **Python com Flask**, com interface em **HTML, CSS e JavaScript** e implantação via **Docker Compose**.

## Executar a edição de portfólio

Com o Docker e o Docker Compose disponíveis, execute na raiz do repositório:

```sh
docker compose up --build
```

Abra [http://localhost:5000](http://localhost:5000). A configuração padrão verifica o próprio portal por HTTP. As métricas exibidas na demonstração correspondem ao ambiente acessível ao contêiner.

Para apontar a verificação a outro serviço de teste, passe `DEMO_SERVICE_URL` ao serviço `portal` no `docker-compose.yml`. O endereço precisa ser acessível de dentro do contêiner.
