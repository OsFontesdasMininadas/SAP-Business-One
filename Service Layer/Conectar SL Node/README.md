<h3>Instala localmente o axios</h3>

npm install axios --save

<h3>//Instancia Biblioteca Axios: https://www.npmjs.com/package/axios  https://github.com/axios/axios e https://axios-http.com/docs/intro</h3>

const axios = require('axios');

<h3>//Instancia https</h3>

const https = require('https');

<h3>//Declara variavel para não ser exigido o SSL para autentificar</h3>

const agent  = new https.Agent({  
    rejectUnauthorized: false
    
  });


    /*Documentação padrão Service Layer https://localhost:50000/

        Exemplo da Chamada realizada para realizar o login 
        
        POST https://localhost:50000/b1s/v1/Login

        {
            "CompanyDB": "SBODEMOUS",
            "Password": "1234",
            "UserName": "manager"
        }



    */

<h3>//Configurações do body para a Chamada de login</h3>

let data = JSON.stringify({
  "CompanyDB": "SBODemoBR_PL04",
  "UserName": "manager",
  "Password": "1234"
});

<h3>//Configurações para a Chamada montando o header e Body</h3>

let config = {
  method: 'post',
  url: 'https://consultsap:50000/b1s/v1/Login',
  httpsAgent: agent,
  headers: { 
    'Content-Type': 'application/json'
  },
  data : data
};



<h3>//Monta a chamada e executa</h3>

axios(config)
//Retorno caso a chamada tenha ocorrido com sucesso

.then(function (response) {
  console.log(JSON.stringify(response.data));
})

//Retorno de erro 
.catch(function (error) {
  console.log(error);
}); 
