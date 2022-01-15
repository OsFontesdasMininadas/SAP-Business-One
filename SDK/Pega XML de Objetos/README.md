
Processo para pegar dados um Objetos e Exporta em XML  


                //Declara oCompany para Pega Empresa Conectada
                SAPbobsCOM.Company oCompany = (SAPbobsCOM.Company)Application.SBO_Application.Company.GetDICompany();

                //instancia obj
                SAPbobsCOM.Documents oInvoices = (SAPbobsCOM.Documents)oCompany.GetBusinessObject(SAPbobsCOM.BoObjectTypes.oInvoices);

                oInvoices.GetByKey(167);

                //Exporta as informações em XML
                oInvoices.SaveXML("C:\\Ramo\\temp.xml");

