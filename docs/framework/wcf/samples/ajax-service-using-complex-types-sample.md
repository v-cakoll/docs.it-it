---
title: Esempio di servizio AJAX che usa tipi complessi
ms.date: 03/30/2017
ms.assetid: 88242b99-4811-4cbe-8201-52ddf48fb174
ms.openlocfilehash: 4227446e8844accd06490d8e7cf933da43d875a6
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84575914"
---
# <a name="ajax-service-using-complex-types-sample"></a>Esempio di servizio AJAX che usa tipi complessi

In questo esempio viene illustrato come utilizzare Windows Communication Foundation (WCF) per creare un servizio AJAX (ASP.NET Asynchronous JavaScript and XML) che crea istanze di tipi complessi e li invia tra servizio e client come JavaScript Object Notation (JSON). È possibile accedere a un servizio AJAX utilizzando codice JavaScript a partire da un client del browser Web. Questo esempio si basa sull'esempio di [servizio AJAX di base](basic-ajax-service.md) .

Il supporto AJAX in WCF è ottimizzato per l'uso con ASP.NET AJAX tramite il <xref:System.Web.UI.ScriptManager> controllo. Per un esempio di utilizzo di WCF con ASP.NET AJAX, vedere gli [esempi di AJAX](ajax.md).

> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.

Il servizio nell'esempio seguente è un servizio WCF senza codice specifico per AJAX. Perché l'attributo <xref:System.ServiceModel.Web.WebGetAttribute> non è applicato, viene utilizzato il verbo HTTP predefinito ("POST"). Il servizio ha un'operazione, `DoMath` che restituisce un tipo complesso denominato `MathResult`. Il tipo complesso è un tipo di contratto dati standard che non contiene codice AJAX specifico.

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

La pagina Web ComplexTypeClientPage. aspx del client contiene il codice ASP.NET e JavaScript per richiamare il servizio quando l'utente fa clic sul pulsante **Esegui calcolo** nella pagina. Il codice per richiamare il servizio costruisce un corpo JSON e lo invia usando HTTP POST, simile al [servizio AJAX che usa l'esempio http post](ajax-service-using-http-post.md) .

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

1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

2. Compilare la soluzione ComplexTypeAjaxService. sln come descritto in [compilazione degli esempi di Windows Communication Foundation](building-the-samples.md).

3. Passare a `http://localhost/ServiceModelSamples/ComplexTypeClientPage.aspx` (non aprire ComplexTypeClientPage. aspx nel browser dalla directory del progetto).

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ComplexTypeAjaxService`

## <a name="see-also"></a>Vedere anche

- [Servizio AJAX di base](basic-ajax-service.md)
