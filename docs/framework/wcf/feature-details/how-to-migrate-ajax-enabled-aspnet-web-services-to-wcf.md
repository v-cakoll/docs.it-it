---
title: 'Procedura: eseguire la migrazione di servizi Web ASP.NET compatibili AJAX a WCF'
ms.date: 03/30/2017
ms.assetid: 1428df4d-b18f-4e6d-bd4d-79ab3dd5147c
ms.openlocfilehash: 6f356f47922945218e02271371d9ddea36ecc5a2
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597007"
---
# <a name="how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf"></a>Procedura: eseguire la migrazione di servizi Web ASP.NET compatibili AJAX a WCF
In questo argomento vengono descritte le procedure per eseguire la migrazione di un servizio ASP.NET AJAX di base a un servizio Windows Communication Foundation (WCF) con supporto AJAX equivalente. Viene illustrato come creare una versione WCF equivalente dal punto di vista funzionale di un servizio ASP.NET AJAX. I due servizi possono quindi essere utilizzati side-by-side oppure il servizio WCF può essere utilizzato per sostituire il servizio ASP.NET AJAX.

 La migrazione di un servizio ASP.NET AJAX esistente a un servizio WCF AJAX offre i vantaggi seguenti:

- È possibile esporre il servizio AJAX come servizio SOAP tramite una minima configurazione aggiuntiva.

- È possibile trarre vantaggio dalle funzionalità WCF, ad esempio la traccia e così via.

 Nelle procedure riportate di seguito si presuppone che si utilizzi Visual Studio 2012.

 Il codice generato dalle procedure descritte in questo argomento viene fornito nell'esempio riportato dopo le procedure stesse.

 Per altre informazioni sull'esposizione di un servizio WCF tramite un endpoint abilitato per AJAX, vedere l'argomento [procedura: usare la configurazione per aggiungere un endpoint ASP.NET AJAX](how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) .

### <a name="to-create-and-test-the-aspnet-web-service-application"></a>Per creare e testare l'applicazione del servizio Web ASP.NET

1. Aprire Visual Studio 2012.

2. Scegliere **nuovo**dal menu **file** , quindi **progetto**, **Web**e quindi selezionare **applicazione servizio Web ASP.NET**.

3. Assegnare un nome al progetto `ASPHello` e fare clic su **OK**.

4. Rimuovere il commento dalla riga nel file Service1.asmx.cs che contiene `System.Web.Script.Services.ScriptService]` per abilitare AJAX per questo servizio.

5. Scegliere **Compila soluzione**dal menu **Compila** .

6. Scegliere **Avvia senza eseguire debug** dal menu **Debug**.

7. Nella pagina Web generata, selezionare l'operazione `HelloWorld`.

8. Fare clic sul pulsante **richiama** nella `HelloWorld` pagina test. Si dovrebbe ricevere la risposta XML seguente:

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <string xmlns="http://tempuri.org/">Hello World</string>
    ```

9. Questa risposta conferma che si dispone di un servizio ASP.NET.AJAX funzionante e, in particolare, che il servizio ha esposto un endpoint su Service1.asmx/HelloWorld che risponde alle richieste HTTP POST e restituisce XML.

     A questo punto si è pronti per convertire il servizio per l'utilizzo di un servizio WCF AJAX.

### <a name="to-create-an-equivalent-wcf-ajax-service-application"></a>Per creare un'applicazione di servizio AJAX WCF equivalente

1. Fare clic con il pulsante destro del mouse sul progetto **ASPHello** , scegliere **Aggiungi**, quindi **nuovo elemento**, quindi **servizio WCF abilitato per AJAX**.

2. Assegnare un nome al servizio `WCFHello` e fare clic su **Aggiungi**.

3. Aprire il file WCFHello.svc.cs.

4. Da Service1.asmx.cs, copiare la seguente implementazione dell' `HelloWorld` operazione.

    ```csharp
    public string HelloWorld()
    {
        return "Hello World";
    }
    ```

5. Incollare nell'implementazione copiata dell' `HelloWorld` operazione nel file WCFHello.svc.cs al posto del codice seguente.

    ```csharp
    public void DoWork()
    {
          // Add your operation implementation here
          return;
    }
    ```

6. Specificare l' `Namespace` attributo per <xref:System.ServiceModel.ServiceContractAttribute> come `WCFHello` .

    ```csharp
    [ServiceContract(Namespace="WCFHello")]
    [AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Required)]
    public class WCFHello
    { … }
    ```

7. Aggiungere all' <xref:System.ServiceModel.Web.WebInvokeAttribute> `HelloWorld` operazione e impostare la <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A> proprietà su Return <xref:System.ServiceModel.Web.WebMessageFormat.Xml> . Se non impostato, il tipo restituito predefinito è <xref:System.ServiceModel.Web.WebMessageFormat.Json>.

    ```csharp
    [OperationContract]
    [WebInvoke(ResponseFormat=WebMessageFormat.Xml)]
    public string HelloWorld()
    {
        return "Hello World";
    }
    ```

8. Scegliere **Compila soluzione**dal menu **Compila** .

9. Aprire il file WCFHello. svc e scegliere **Avvia senza eseguire debug**dal menu **debug** .

10. Il servizio espone ora un endpoint in `WCFHello.svc/HelloWorld` , che risponde alle richieste HTTP post. Le richieste HTTP POST non possono essere sottoposte a test dal browser, ma l'endpoint restituisce l'XML seguente.

    ```xml
    <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/">Hello World</string>
    ```

11. Gli `WCFHello.svc/HelloWorld` endpoint e `Service1.aspx/HelloWorld` sono ora funzionalmente equivalenti.

## <a name="example"></a>Esempio
 Il codice che scaturisce dalle procedure descritte in questo argomento viene fornito nell'esempio seguente.

```csharp
//This is the ASP.NET code in the Service1.asmx.cs file.

using System;
using System.Collections;
using System.ComponentModel;
using System.Data;
using System.Linq;
using System.Web;
using System.Web.Services;
using System.Web.Services.Protocols;
using System.Xml.Linq;
using System.Web.Script.Services;

namespace ASPHello
{
    /// <summary>
    /// Summary description for Service1.
    /// </summary>
    [WebService(Namespace = "http://tempuri.org/")]
    [WebServiceBinding(ConformsTo = WsiProfiles.BasicProfile1_1)]
    [ToolboxItem(false)]
    // To allow this Web Service to be called from script, using ASP.NET AJAX, uncomment the following line.
    [System.Web.Script.Services.ScriptService]
    public class Service1 : System.Web.Services.WebService
    {

        [WebMethod]
        public string HelloWorld()
        {
            return "Hello World";
        }
    }
}

//This is the WCF code in the WCFHello.svc.cs file.
using System;
using System.Linq;
using System.Runtime.Serialization;
using System.ServiceModel;
using System.ServiceModel.Activation;
using System.ServiceModel.Web;

namespace ASPHello
{
    [ServiceContract(Namespace = "WCFHello")]
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class WCFHello
    {
        // Add [WebInvoke] attribute to use HTTP GET.
        [OperationContract]
        [WebInvoke(ResponseFormat=WebMessageFormat.Xml)]
        public string HelloWorld()
        {
            return "Hello World";
        }

        // Add more operations here and mark them with [OperationContract].
    }
}
```

 Il tipo <xref:System.Xml.XmlDocument> non è supportato da <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> perché non è serializzabile mediante <xref:System.Xml.Serialization.XmlSerializer>. È possibile utilizzare un tipo <xref:System.Xml.Linq.XDocument> oppure serializzare <xref:System.Xml.XmlDocument.DocumentElement%2A>.

 Se i servizi Web ASMX vengono aggiornati e migrati side-by-Side ai servizi WCF, evitare di eseguire il mapping di due tipi con lo stesso nome nel client. Se viene utilizzato lo stesso tipo sia in un <xref:System.Web.Services.WebMethodAttribute> che in un <xref:System.ServiceModel.ServiceContractAttribute>, nei serializzatori verrà generata un'eccezione:

- Se il servizio WCF viene aggiunto per primo, la chiamata del metodo nel servizio Web ASMX causa un'eccezione in <xref:System.Web.UI.ObjectConverter.ConvertValue%28System.Object%2CSystem.Type%2CSystem.String%29> perché la definizione di stile WCF dell'ordine nel proxy ha la precedenza.

- Se il servizio Web ASMX viene aggiunto per primo, la chiamata al metodo sul servizio WCF causa un'eccezione in <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> perché la definizione di stile del servizio Web dell'ordine nel proxy ha la precedenza.

 Esistono differenze significative di comportamento tra <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> e <xref:System.Web.Script.Serialization.JavaScriptSerializer> ASP.NET AJAX. <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, ad esempio, rappresenta un dizionario come una matrice di coppie chiave/valore, mentre ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer> rappresenta un dizionario come oggetti JSON effettivi. Pertanto quello seguente è il dizionario rappresentato in ASP.NET AJAX.

```csharp
Dictionary<string, int> d = new Dictionary<string, int>();
d.Add("one", 1);
d.Add("two", 2);
```

 Tale dizionario è rappresentato negli oggetti JSON come mostrato nell'elenco seguente:

- [{"Key":"one","Value":1},{"Key":"two","Value":2}] da <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>

- {"One": 1, "Two": 2} da ASP.NET AJAX<xref:System.Web.Script.Serialization.JavaScriptSerializer>

 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> è più potente perché può gestire dizionari in cui il tipo di chiave non è una stringa, mentre <xref:System.Web.Script.Serialization.JavaScriptSerializer> non è in grado di farlo. Quest'ultimo, tuttavia, è più favorevole a JSON.

 Le differenze significative tra questi serializzatori sono riepilogate nella tabella seguente.

|Categoria delle differenze|DataContractJsonSerializer|JavaScriptSerializer per ASP.NET AJAX|
|-----------------------------|--------------------------------|---------------------------------------|
|Deserializzazione del buffer vuoto (new byte[0]) in <xref:System.Object> (o <xref:System.Uri> o alcune altre classi).|SerializationException|Null|
|Serializzazione di <xref:System.DBNull.Value>|{}(o {"__type": "#System"})|Null|
|Serializzazione dei membri privati di tipi [Serializable].|serializzato|non serializzato|
|Serializzazione delle proprietà pubbliche di tipi <xref:System.Runtime.Serialization.ISerializable>.|non serializzato|serializzato|
|"Estensioni" di JSON|È conforme alla specifica JSON, che richiede le virgolette per i nomi dei membri di un oggetto ({"a":"hello"}).|Supporta i nomi dei membri di un oggetto senza virgolette ({a:"hello"}).|
|Ora UTC (Coordinated Universal Time) <xref:System.DateTime>|Non supporta il formato " \\ /date (123456789U) \\ /" o " \\ /date \\ (\d + (U&#124; ( \\ + \\ -[\d {4} ])). \\ \\ \\ /)".|Supporta il formato " \\ /date (123456789U) \\ /" e " \\ /date \\ (\d + (U&#124; ( \\ + \\ -[\d {4} ])) \\ . \\ \\ /) "come valori DateTime.|
|Rappresentazione di dizionari|Una matrice di KeyValuePair \<K,V> , gestisce i tipi di chiave che non sono stringhe.|Come gli oggetti JSON effettivi, ma gestisce solo i tipi di chiave che sono stringhe.|
|Caratteri di escape|Sempre con un carattere di escape barra (/); non consente mai caratteri JSON non validi senza carattere di escape, ad esempio "\n".|Con un carattere di escape barra (/) per i valori DateTime.|

## <a name="see-also"></a>Vedere anche

- [Procedura: aggiungere un endpoint ASP.NET AJAX con l'uso della configurazione](how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)
