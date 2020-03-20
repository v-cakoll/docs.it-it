---
title: 'Procedura: creare un servizio che restituisca dati arbitrari usando il modello di programmazione HTTP Web WCF'
ms.date: 03/30/2017
ms.assetid: 0283955a-b4ae-458d-ad9e-6fbb6f529e3d
ms.openlocfilehash: c85ab6725876a2d523a18c817ce3fd89f0d2285a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184478"
---
# <a name="how-to-create-a-service-that-returns-arbitrary-data-using-the-wcf-web-http-programming-model"></a>Procedura: creare un servizio che restituisca dati arbitrari usando il modello di programmazione HTTP Web WCF
Talvolta gli sviluppatori devono disporre del controllo completo sulla modalità di restituzione dei dati da un'operazione del servizio, Ciò avviene quando un'operazione del servizio deve restituire dati in un formato non supportato da WCF. In questo argomento viene illustrato l'utilizzo del modello di programmazione HTTP WEB WCF per creare un servizio di questo tipo. In questo servizio è presente un'operazione che restituisce un flusso.  
  
### <a name="to-implement-the-service-contract"></a>Per implementare il contratto di servizio  
  
1. Definire il contratto di servizio. Il contratto viene denominato `IImageServer` e dispone di un metodo chiamato `GetImage` che restituisce <xref:System.IO.Stream>.  
  
    ```csharp  
    [ServiceContract]  
        public interface IImageServer  
        {  
            [WebGet]  
            Stream GetImage(int width, int height);  
        }  
    ```  
  
     Poiché il <xref:System.IO.Stream>metodo restituisce un oggetto , WCF presuppone che l'operazione abbia il controllo completo sui byte restituiti dall'operazione del servizio e non applica alcuna formattazione ai dati restituiti.  
  
2. Implementare il contratto di servizio Il contratto ha una sola operazione (`GetImage`). Questo metodo genera una bitmap, quindi la salva in <xref:System.IO.MemoryStream> in formato .jpg. L'operazione restituisce quindi il flusso al chiamante.  
  
    ```csharp
    public class Service : IImageServer
    {
        public Stream GetImage(int width, int height)
        {
            Bitmap bitmap = new Bitmap(width, height);
            for (int i = 0; i < bitmap.Width; i++)
            {
                for (int j = 0; j < bitmap.Height; j++)
                {
                    bitmap.SetPixel(i, j, (Math.Abs(i - j) < 2) ? Color.Blue : Color.Yellow);
                }
            }
            MemoryStream ms = new MemoryStream();
            bitmap.Save(ms, System.Drawing.Imaging.ImageFormat.Jpeg);
            ms.Position = 0;
            WebOperationContext.Current.OutgoingResponse.ContentType = "image/jpeg";
            return ms;
        }
    }
    ```  
  
     Si noti il codice dalla seconda all'ultima riga: `WebOperationContext.Current.OutgoingResponse.ContentType = "image/jpeg";`  
  
     In questo modo l'intestazione del tipo di contenuto viene impostata `"image/jpeg"`su . Sebbene in questo esempio venga illustrato come restituire un file jpg, è possibile modificarlo per restituire qualsiasi tipo di dati necessario, in qualsiasi formato. L'operazione deve recuperare o generare i dati e scriverli in un flusso.  
  
### <a name="to-host-the-service"></a>Per ospitare il servizio  
  
1. Creare un'applicazione console per ospitare il servizio.  
  
    ```csharp
    class Program  
    {  
        static void Main(string[] args)  
        {  
        }
    }  
    ```  
  
2. Creare una variabile per contenere l'indirizzo di base per il servizio all'interno del metodo `Main`.  
  
    ```csharp
    string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
    ```  
  
3. Creare un'istanza di <xref:System.ServiceModel.ServiceHost> per il servizio specificando la classe e l'indirizzo di base del servizio.  
  
    ```csharp
    ServiceHost host = new ServiceHost(typeof(Service), new Uri(baseAddress));  
    ```  
  
4. Aggiungere un endpoint utilizzando <xref:System.ServiceModel.WebHttpBinding> e <xref:System.ServiceModel.Description.WebHttpBehavior>.  
  
    ```csharp  
    host.AddServiceEndpoint(typeof(IImageServer), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
    ```  
  
5. Aprire l’host del servizio.  
  
    ```csharp  
    host.Open();  
    ```  
  
6. Attendere che l'utente prema INVIO prima di terminare il servizio.  
  
    ```csharp
    Console.WriteLine("Service is running");  
    Console.Write("Press ENTER to close the host");  
    Console.ReadLine();  
    host.Close();  
    ```  
  
### <a name="to-call-the-raw-service-using-internet-explorer"></a>Per chiamare il servizio non elaborato tramite Internet Explorer  
  
1. Eseguire il servizio. L'output seguente dovrebbe essere restituito dal servizio. `Service is running Press ENTER to close the host`  
  
2. Aprire Internet Explorer e digitare `http://localhost:8000/Service/GetImage?width=50&height=40`. Verrà visualizzato un rettangolo giallo con una linea diagonale blu che attraversa il centro.  
  
## <a name="example"></a>Esempio  
 Di seguito è riportato un elenco completo del codice per questo argomento.  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.ServiceModel;  
using System.ServiceModel.Web;  
using System.ServiceModel.Description;  
using System.IO;  
using System.Drawing;  
  
namespace RawImageService  
{  
    // Define the service contract  
    [ServiceContract]  
    public interface IImageServer  
    {  
        [WebGet]  
        Stream GetImage(int width, int height);  
    }  
  
    // implement the service contract  
    public class Service : IImageServer  
    {  
        public Stream GetImage(int width, int height)  
        {  
            // Although this method returns a jpeg, it can be  
            // modified to return any data you want within the stream  
            Bitmap bitmap = new Bitmap(width, height);  
            for (int i = 0; i < bitmap.Width; i++)  
            {  
                for (int j = 0; j < bitmap.Height; j++)  
                {  
                    bitmap.SetPixel(i, j, (Math.Abs(i - j) < 2) ? Color.Blue : Color.Yellow);  
                }  
            }  
            MemoryStream ms = new MemoryStream();  
            bitmap.Save(ms, System.Drawing.Imaging.ImageFormat.Jpeg);  
            ms.Position = 0;  
            WebOperationContext.Current.OutgoingResponse.ContentType = "image/jpeg";  
            return ms;  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
            ServiceHost host = new ServiceHost(typeof(Service), new Uri(baseAddress));  
            host.AddServiceEndpoint(typeof(IImageServer), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
            host.Open();  
            Console.WriteLine("Service is running");  
            Console.Write("Press ENTER to close the host");  
            Console.ReadLine();  
            host.Close();  
  
        }  
    }  
}  
```  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
- Durante la compilazione del codice di esempio, fare riferimento a System.ServiceModel.dll e a System.ServiceModel.Web.dll.  
  
## <a name="see-also"></a>Vedere anche

- [Modello di programmazione HTTP Web WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
