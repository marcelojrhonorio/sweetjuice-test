# Desafio
## _Estágio em Desenvolvimento Unity na Sweet Media_

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

Você deve desenvolver um simples formulário em Unity que acesse a API disponibilizada abaixo. O objetivo é capturar os dados do formulário e enviar para a API. 
O formulário terá os seguinte campos: 

- `nome completo`
- `email`
- `data de nascimento` (dd-mm-aaaa)

**OBS: Todos os campos são obrigatórios e a validação dos campos email e data de nascimento faz parte do processo seletivo.**

## Requisitos essenciais

- Usar a versão `2019.4.15f1` da Unity
- O formulário deve estar na dimensão **1080x1920**
- O projeto deve estar totalmente pronto pronto para buildar para Android

## Endpoint para recebimento de dados
Os dados do formulário devem ser enviados para a seguinte URL:
```
https://sweetbonus.com.br/sweet-juice/trainee-test/submit?candidate={SEU_PRIMEIRO_NOME}&fullname={NOME_COMPLETO_DO_FORMULARIO}&email={EMAIL_DO_FORMULARIO}&birthdate={DATA_NASCIMENTO_DO_FORMULARIO}
```
Observe que o parâmetro `candidate` recebe um valor fixo que é **seu primeiro nome com todas as letras minúsculas**.

### Possíveis retornos da API

Caso todos os campos estejam correto, o seguinte json será retornado. Leia-o e mostre uma mensagem de obrigado.
```json
{
    "success": true,
    "status": "success",
    "data": {
        "message": "Dados recebidos com sucesso!"
    }
}
```

Retornos json que indicam que algum dado está incorreto ou faltante: 
```json
{
    "success": false,
    "status": "empty_fullname",
    "data": []
}
```

```json
{
    "success": false,
    "status": "empty_email",
    "data": []
}
```

```json
{
    "success": false,
    "status": "empty_birthdate",
    "data": []
}
```


