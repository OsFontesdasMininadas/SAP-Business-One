<h2>Instala localmente o axios</h2>
npm install axios --save

<h2>//Instancia Biblioteca Axios: https://www.npmjs.com/package/axios  https://github.com/axios/axios e https://axios-http.com/docs/intro</h2>
const axios = require('axios');

<h2>//Instancia https</h2>
const https = require('https');

<h2>//Declara variavel para não ser exigido o SSL para autentificar</h2>
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

<h2>//Configurações do body para a Chamada de login</h2>
let data = JSON.stringify({
  "CompanyDB": "SBODemoBR_PL04",
  "UserName": "manager",
  "Password": "1234"
});

<h2>//Configurações para a Chamada montando o header e Body</h2>
let config = {
  method: 'post',
  url: 'https://consultsap:50000/b1s/v1/Login',
  httpsAgent: agent,
  headers: { 
    'Content-Type': 'application/json'
  },
  data : data
};



<h2>//Monta a chamada e executa</h2>
axios(config)
//Retorno caso a chamada tenha ocorrido com sucesso
.then(function (response) {
  console.log(JSON.stringify(response.data));
})
//Retorno de erro 
.catch(function (error) {
  console.log(error);
}); 
