Pega a Instacia Logada para execução do Add-on



Instancia Empresa atual em Program para utilizar de forma Global no Código:

public static SAPbobsCOM.Company oCompany = null;

oCompany = ((SAPbobsCOM.Company)SAPbouiCOM.Framework.Application.SBO_Application.Company.GetDICompany());


Exemplo:

![image](https://user-images.githubusercontent.com/91930440/147935553-516463c6-c3bc-46af-9012-26bae7888923.png)



Para utilizar Chame a clase Program e oCompany?

Program.oCompany