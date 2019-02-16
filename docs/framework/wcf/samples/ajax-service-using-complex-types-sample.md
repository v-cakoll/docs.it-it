---
title: Esempio di servizio AJAX che usa tipi complessi
ms.date: 03/30/2017
ms.assetid: 88242b99-4811-4cbe-8201-52ddf48fb174
ms.openlocfilehash: 17c760c8276799fed7e7a8366c17ef9f5cf7081c
ms.sourcegitcommit: 0069cb3de8eed4e92b2195d29e5769a76111acdd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/16/2019
ms.locfileid: "56333482"
---
# <a name="ajax-service-using-complex-types-sample"></a>Esempio di servizio AJAX che usa tipi complessi
Questo esempio viene illustrato come utilizzare Windows Communication Foundation (WCF) per creare un servizio ASP.NET Asynchronous JavaScript and XML (AJAX) che crea istanze di tipi complessi e li invia tra servizio e client come JavaScript Object Notation (JSON). È possibile accedere a un servizio AJAX utilizzando codice JavaScript a partire da un client del browser Web. In questo esempio si basa sul [servizio AJAX di base](../../../../docs/framework/wcf/samples/basic-ajax-service.md) esempio.  
  
 Supporto AJAX in WCF è ottimizzato per l'utilizzo con ASP.NET AJAX tramite il <xref:System.Web.UI.ScriptManager> controllo. Per un esempio dell'utilizzo di WCF con ASP.NET AJAX, vedere la [esempi AJAX](ajax.md).  
  
> [!NOTE]
>  La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 Il servizio nell'esempio seguente è un servizio WCF senza codice AJAX specifico. Perché l'attributo <xref:System.ServiceModel.Web.WebGetAttribute> non è applicato, viene utilizzato il verbo HTTP predefinito ("POST"). Il servizio ha un'operazione, `DoMath` che restituisce un tipo complesso denominato `MathResult`. Il tipo complesso è un tipo di contratto dati standard che non contiene codice AJAX specifico.  

```csharp
[DataContract]  
public class MathResult  
{  
    [DataMember]  
    public double sum;  
    [DataMember]  
    public double difference;  
    [DataMember]  
    public double product;  
    [DataMember]  
    public double quotient;  
}  
```

 Creare un endpoint AJAX sul servizio utilizzando <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, proprio come nell'esempio del servizio AJAX di base.  
  
 La pagina Web complextypeclientpage. aspx del client contiene il codice ASP.NET e JavaScript per richiamare il servizio quando l'utente fa clic il **eseguire il calcolo** pulsante nella pagina. Il codice per richiamare il servizio costruisce un corpo JSON e lo invia utilizzando HTTP POST, simile al [servizio AJAX con HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) esempio.  
  
 Dopo che la chiamata del servizio riesce, è possibile accedere ai membri dati singoli (`sum`, `difference`, `product` e `quotient`) sull'oggetto JavaScript risultante.  

```javascript
function onSuccess(mathResult){  
     document.getElementById("sum").value = mathResult.sum;  
     document.getElementById("difference").value = mathResult.difference;  
     document.getElementById("product").value = mathResult.product;  
     document.getElementById("quotient").value = mathResult.quotient;  
}  
```

### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Compilare la soluzione Complextypeajaxservice come descritto in [Building Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Passare a `http://localhost/ServiceModelSamples/ComplexTypeClientPage.aspx` (non aprire complextypeclientpage. aspx nel browser dalla directory del progetto).  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ComplexTypeAjaxService`  
  
## <a name="see-also"></a>Vedere anche
- [Servizio AJAX di base](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
