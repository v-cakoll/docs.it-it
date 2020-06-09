---
title: 'Procedura: creare un servizio che restituisca dati arbitrari usando il modello di programmazione HTTP Web WCF'
ms.date: 03/30/2017
ms.assetid: 0283955a-b4ae-458d-ad9e-6fbb6f529e3d
ms.openlocfilehash: 9753fbc9b333cb7e89ddc8dff030cb1f62ede23b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600361"
---
# <a name="how-to-create-a-service-that-returns-arbitrary-data-using-the-wcf-web-http-programming-model"></a><span data-ttu-id="97d90-102">Procedura: creare un servizio che restituisca dati arbitrari usando il modello di programmazione HTTP Web WCF</span><span class="sxs-lookup"><span data-stu-id="97d90-102">How to: Create a Service That Returns Arbitrary Data Using The WCF Web HTTP Programming Model</span></span>
<span data-ttu-id="97d90-103">Talvolta gli sviluppatori devono disporre del controllo completo sulla modalità di restituzione dei dati da un'operazione del servizio,</span><span class="sxs-lookup"><span data-stu-id="97d90-103">Sometimes developers must have full control of how data is returned from a service operation.</span></span> <span data-ttu-id="97d90-104">Questa situazione si verifica quando un'operazione del servizio deve restituire dati in un formato non supportato da WCF.</span><span class="sxs-lookup"><span data-stu-id="97d90-104">This is the case when a service operation must return data in a format not supported by WCF.</span></span> <span data-ttu-id="97d90-105">In questo argomento viene illustrato l'utilizzo del modello di programmazione HTTP WEB WCF per creare un servizio di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="97d90-105">This topic discusses using the WCF WEB HTTP Programming Model to create such a service.</span></span> <span data-ttu-id="97d90-106">In questo servizio è presente un'operazione che restituisce un flusso.</span><span class="sxs-lookup"><span data-stu-id="97d90-106">This service has one operation that returns a stream.</span></span>  
  
### <a name="to-implement-the-service-contract"></a><span data-ttu-id="97d90-107">Per implementare il contratto di servizio</span><span class="sxs-lookup"><span data-stu-id="97d90-107">To implement the service contract</span></span>  
  
1. <span data-ttu-id="97d90-108">Definire il contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="97d90-108">Define the service contract.</span></span> <span data-ttu-id="97d90-109">Il contratto viene denominato `IImageServer` e dispone di un metodo chiamato `GetImage` che restituisce <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="97d90-109">The contract is called `IImageServer` and has one method called `GetImage` that returns a <xref:System.IO.Stream>.</span></span>  
  
    ```csharp  
    [ServiceContract]  
        public interface IImageServer  
        {  
            [WebGet]  
            Stream GetImage(int width, int height);  
        }  
    ```  
  
     <span data-ttu-id="97d90-110">Poiché il metodo restituisce un oggetto <xref:System.IO.Stream> , WCF presuppone che l'operazione abbia il controllo completo sui byte restituiti dall'operazione del servizio e non applica la formattazione ai dati restituiti.</span><span class="sxs-lookup"><span data-stu-id="97d90-110">Because the method returns a <xref:System.IO.Stream>, WCF assumes that the operation has complete control over the bytes that are returned from the service operation and it applies no formatting to the data that is returned.</span></span>  
  
2. <span data-ttu-id="97d90-111">Implementare il contratto di servizio</span><span class="sxs-lookup"><span data-stu-id="97d90-111">Implement the service contract.</span></span> <span data-ttu-id="97d90-112">Il contratto ha una sola operazione (`GetImage`).</span><span class="sxs-lookup"><span data-stu-id="97d90-112">The contract has only one operation (`GetImage`).</span></span> <span data-ttu-id="97d90-113">Questo metodo genera una bitmap, quindi la salva in <xref:System.IO.MemoryStream> in formato .jpg.</span><span class="sxs-lookup"><span data-stu-id="97d90-113">This method generates a bitmap and then save it to a <xref:System.IO.MemoryStream> in .jpg format.</span></span> <span data-ttu-id="97d90-114">L'operazione restituisce quindi il flusso al chiamante.</span><span class="sxs-lookup"><span data-stu-id="97d90-114">The operation then returns that stream to the caller.</span></span>  
  
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
  
     <span data-ttu-id="97d90-115">Si noti il codice dalla seconda all'ultima riga: `WebOperationContext.Current.OutgoingResponse.ContentType = "image/jpeg";`</span><span class="sxs-lookup"><span data-stu-id="97d90-115">Notice the second to last line of code: `WebOperationContext.Current.OutgoingResponse.ContentType = "image/jpeg";`</span></span>  
  
     <span data-ttu-id="97d90-116">In questo modo l'intestazione del tipo di contenuto viene impostata su `"image/jpeg"` .</span><span class="sxs-lookup"><span data-stu-id="97d90-116">This sets the content type header to `"image/jpeg"`.</span></span> <span data-ttu-id="97d90-117">Sebbene in questo esempio venga illustrato come restituire un file jpg, è possibile modificarlo per restituire qualsiasi tipo di dati necessario, in qualsiasi formato.</span><span class="sxs-lookup"><span data-stu-id="97d90-117">Although this sample shows how to return a .jpg file, it can be modified to return any type of data that is required, in any format.</span></span> <span data-ttu-id="97d90-118">L'operazione deve recuperare o generare i dati e scriverli in un flusso.</span><span class="sxs-lookup"><span data-stu-id="97d90-118">The operation must retrieve or generate the data and then write it to a stream.</span></span>  
  
### <a name="to-host-the-service"></a><span data-ttu-id="97d90-119">Per ospitare il servizio</span><span class="sxs-lookup"><span data-stu-id="97d90-119">To host the service</span></span>  
  
1. <span data-ttu-id="97d90-120">Creare un'applicazione console per ospitare il servizio.</span><span class="sxs-lookup"><span data-stu-id="97d90-120">Create a console application to host the service.</span></span>  
  
    ```csharp
    class Program  
    {  
        static void Main(string[] args)  
        {  
        }
    }  
    ```  
  
2. <span data-ttu-id="97d90-121">Creare una variabile per contenere l'indirizzo di base per il servizio all'interno del metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="97d90-121">Create a variable to hold the base address for the service within the `Main` method.</span></span>  
  
    ```csharp
    string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
    ```  
  
3. <span data-ttu-id="97d90-122">Creare un'istanza di <xref:System.ServiceModel.ServiceHost> per il servizio specificando la classe e l'indirizzo di base del servizio.</span><span class="sxs-lookup"><span data-stu-id="97d90-122">Create a <xref:System.ServiceModel.ServiceHost> instance for the service specifying the service class and the base address.</span></span>  
  
    ```csharp
    ServiceHost host = new ServiceHost(typeof(Service), new Uri(baseAddress));  
    ```  
  
4. <span data-ttu-id="97d90-123">Aggiungere un endpoint utilizzando <xref:System.ServiceModel.WebHttpBinding> e <xref:System.ServiceModel.Description.WebHttpBehavior>.</span><span class="sxs-lookup"><span data-stu-id="97d90-123">Add an endpoint using the <xref:System.ServiceModel.WebHttpBinding> and the <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span>  
  
    ```csharp  
    host.AddServiceEndpoint(typeof(IImageServer), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
    ```  
  
5. <span data-ttu-id="97d90-124">Aprire l’host del servizio.</span><span class="sxs-lookup"><span data-stu-id="97d90-124">Open the service host.</span></span>  
  
    ```csharp  
    host.Open();  
    ```  
  
6. <span data-ttu-id="97d90-125">Attendere che l'utente prema INVIO prima di terminare il servizio.</span><span class="sxs-lookup"><span data-stu-id="97d90-125">Wait until the user presses ENTER to terminate the service.</span></span>  
  
    ```csharp
    Console.WriteLine("Service is running");  
    Console.Write("Press ENTER to close the host");  
    Console.ReadLine();  
    host.Close();  
    ```  
  
### <a name="to-call-the-raw-service-using-internet-explorer"></a><span data-ttu-id="97d90-126">Per chiamare il servizio non elaborato tramite Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="97d90-126">To call the raw service using Internet Explorer</span></span>  
  
1. <span data-ttu-id="97d90-127">Eseguire il servizio. L'output seguente dovrebbe essere restituito dal servizio.</span><span class="sxs-lookup"><span data-stu-id="97d90-127">Run the service, you should see the following output from the service.</span></span> `Service is running Press ENTER to close the host`  
  
2. <span data-ttu-id="97d90-128">Aprire Internet Explorer e digitare `http://localhost:8000/Service/GetImage?width=50&height=40`. Verrà visualizzato un rettangolo giallo con una linea diagonale blu che attraversa il centro.</span><span class="sxs-lookup"><span data-stu-id="97d90-128">Open Internet Explorer and type in `http://localhost:8000/Service/GetImage?width=50&height=40` you should see a yellow rectangle with a blue diagonal line through the center.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97d90-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="97d90-129">Example</span></span>  
 <span data-ttu-id="97d90-130">Di seguito è riportato un elenco completo del codice per questo argomento.</span><span class="sxs-lookup"><span data-stu-id="97d90-130">The following is a complete listing of the code for this topic.</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="97d90-131">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="97d90-131">Compiling the Code</span></span>  
  
- <span data-ttu-id="97d90-132">Durante la compilazione del codice di esempio, fare riferimento a System.ServiceModel.dll e a System.ServiceModel.Web.dll.</span><span class="sxs-lookup"><span data-stu-id="97d90-132">When compiling the sample code reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97d90-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97d90-133">See also</span></span>

- [<span data-ttu-id="97d90-134">Modello di programmazione HTTP Web WCF</span><span class="sxs-lookup"><span data-stu-id="97d90-134">WCF Web HTTP Programming Model</span></span>](wcf-web-http-programming-model.md)
