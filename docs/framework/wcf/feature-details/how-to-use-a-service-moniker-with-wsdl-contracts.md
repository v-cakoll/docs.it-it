---
title: 'Procedura: usare un moniker di servizio con i contratti WSDL'
ms.date: 03/30/2017
ms.assetid: a88d9650-bb50-4f48-8c85-12f5ce98a83a
ms.openlocfilehash: 70d7e9ff45616f832597ebc48db00198967935c6
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601140"
---
# <a name="how-to-use-a-service-moniker-with-wsdl-contracts"></a>Procedura: usare un moniker di servizio con i contratti WSDL
In alcune situazioni può essere necessario disporre di un client per l'interoperabilità COM completamente autonomo. Il servizio che si desidera chiamare può non esporre un endpoint MEX e la DLL del client WCF può non essere registrata per l'interoperabilità COM. In questi casi è possibile creare un file WSDL che descriva il servizio e lo passi nel moniker del servizio WCF. In questo argomento viene illustrato come chiamare l'esempio WCF della Guida introduttiva utilizzando un moniker WSDL WCF.  
  
### <a name="using-the-wsdl-service-moniker"></a>Utilizzo del moniker del servizio WSDL  
  
1. Aprire e compilare la soluzione di esempio GettingStarted.  
  
2. Aprire Internet Explorer e passare a `http://localhost/ServiceModelSamples/Service.svc` per verificare che il servizio sia funzionante.  
  
3. Nel file Service.cs aggiungere l'attributo seguente alla classe CalculatorService:  
  
     [!code-csharp[S_WSDL_Client#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wsdl_client/cs/service.cs#0)]  
  
4. Aggiungere un spazio dei nomi dell'associazione al servizio App.config:  

5. Creare un file WSDL che deve essere letto dall'applicazione. Poiché gli spazi dei nomi sono stati aggiunti nei passaggi 3 e 4, è possibile utilizzare IE per eseguire una query per l'intera descrizione WSDL del servizio passando a `http://localhost/ServiceModelSamples/Service.svc?wsdl` . È quindi possibile salvare il file da Internet Explorer come serviceWSDL.xml. Se non si specificano gli spazi dei nomi nei passaggi 3 e 4, il documento WSDL restituito dalla query sull'URL precedente non sarà il WSDL completo. Il documento WSDL restituito includerà molte istruzioni di importazione che consentono di importare altri documenti WSDL. Sarà quindi necessario esaminare ogni istruzione di importazione e compilare il documento WSDL completo, combinando il WSDL restituito dal servizio con il WSDL importato.  
  
6. Aprire Visual Basic 6.0 e creare un nuovo file standard con estensione exe. Aggiungere un pulsante al form e fare doppio clic su di esso per aggiungere il codice seguente al gestore Click:  
  
    ```vb
    ' Open the WSDL contract file and read it all into the wsdlContract string.  
    Const ForReading = 1  
    Set objFSO = CreateObject("Scripting.FileSystemObject")  
    Set objFile = objFSO.OpenTextFile("c:\serviceWsdl.xml", ForReading)  
    wsdlContract = objFile.ReadAll  
    objFile.Close  
  
    ' Create a string for the service moniker including the content of the WSDL contract file.  
    wsdlMonikerString = "service4:address='http://localhost/ServiceModelSamples/service.svc'"  
    wsdlMonikerString = wsdlMonikerString + ", wsdl='" & wsdlContract & "'"  
    wsdlMonikerString = wsdlMonikerString + ", binding=WSHttpBinding_ICalculator, bindingNamespace='http://Microsoft.ServiceModel.Samples'"  
    wsdlMonikerString = wsdlMonikerString + ", contract=ICalculator, contractNamespace='http://Microsoft.ServiceModel.Samples'"  
  
    ' Create the service moniker object.  
    Set wsdlServiceMoniker = GetObject(wsdlMonikerString)  
  
    ' Call the service operations using the moniker object.  
    MsgBox "WSDL service moniker: 145 - 76.54 = " & wsdlServiceMoniker.Subtract(145, 76.54)  
    ```  
  
    > [!NOTE]
    > Se il formato del moniker non è valido o se il servizio non è disponibile, la chiamata a `GetObject` restituirà un errore "Sintassi non valida".  Se si riceve questo errore, verificare che il moniker che si sta usando sia valido e che il servizio sia disponibile.  
  
7. Eseguire l'applicazione Visual Basic. Verrà visualizzata una finestra di messaggio con i risultati della chiamata a Subtract(145, 76.54).  
  
## <a name="see-also"></a>Vedere anche

- [Per iniziare](../samples/getting-started-sample.md)
- [Panoramica dell'integrazione con applicazioni COM](integrating-with-com-applications-overview.md)
