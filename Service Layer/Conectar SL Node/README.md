npm install axios --save

//Instancia Biblioteca Axios: https://www.npmjs.com/package/axios  https://github.com/axios/axios e https://axios-http.com/docs/intro
const axios = require('axios');

//Instancia https
const https = require('https');

//Declara variavel para não ser exigido o SSL para autentificar
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

//Configurações do body para a Chamada de login
let data = JSON.stringify({
  "CompanyDB": "SBODemoBR_PL04",
  "UserName": "manager",
  "Password": "1234"
});

//Configurações para a Chamada montando o header e Body
let config = {
  method: 'post',
  url: 'https://consultsap:50000/b1s/v1/Login',
  httpsAgent: agent,
  headers: { 
    'Content-Type': 'application/json'
  },
  data : data
};



//Monta a chamada e executa
axios(config)
//Retorno caso a chamada tenha ocorrido com sucesso
.then(function (response) {
  console.log(JSON.stringify(response.data));
})
//Retorno de erro 
.catch(function (error) {
  console.log(error);
});
