---
title: 'Procedura: creare un servizio che accetti dati arbitrari usando il modello di programmazione REST WCF'
ms.date: 03/30/2017
ms.assetid: e566c15a-b600-4e4a-be3a-4af43e767dae
ms.openlocfilehash: d908651f7815c102b45ea106f5bec4c07d869950
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601335"
---
# <a name="how-to-create-a-service-that-accepts-arbitrary-data-using-the-wcf-rest-programming-model"></a><span data-ttu-id="e8970-102">Procedura: creare un servizio che accetti dati arbitrari usando il modello di programmazione REST WCF</span><span class="sxs-lookup"><span data-stu-id="e8970-102">How to: Create a Service That Accepts Arbitrary Data using the WCF REST Programming Model</span></span>
<span data-ttu-id="e8970-103">Talvolta gli sviluppatori devono disporre del controllo completo sulla modalità di restituzione dei dati da un'operazione del servizio,</span><span class="sxs-lookup"><span data-stu-id="e8970-103">Sometimes developers must have full control of how data is returned from a service operation.</span></span> <span data-ttu-id="e8970-104">Questa situazione si verifica quando un'operazione del servizio deve restituire dati in un formato non supportato byWCF.</span><span class="sxs-lookup"><span data-stu-id="e8970-104">This is the case when a service operation must return data in a format not supported byWCF.</span></span> <span data-ttu-id="e8970-105">In questo argomento viene illustrato l'utilizzo del modello di programmazione WCF REST per creare un servizio che riceve dati arbitrari.</span><span class="sxs-lookup"><span data-stu-id="e8970-105">This topic discusses using the WCF REST Programming Model to create a service that receives arbitrary data.</span></span>  
  
### <a name="to-implement-the-service-contract"></a><span data-ttu-id="e8970-106">Per implementare il contratto di servizio</span><span class="sxs-lookup"><span data-stu-id="e8970-106">To implement the service contract</span></span>  
  
1. <span data-ttu-id="e8970-107">Definire il contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="e8970-107">Define the service contract.</span></span> <span data-ttu-id="e8970-108">L'operazione che riceve i dati arbitrari deve disporre di un parametro di tipo <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="e8970-108">The operation that receives the arbitrary data must have a parameter of type <xref:System.IO.Stream>.</span></span> <span data-ttu-id="e8970-109">Il parametro deve inoltre essere l'unico passato nel corpo della richiesta.</span><span class="sxs-lookup"><span data-stu-id="e8970-109">In addition, this parameter must be the only parameter passed in the body of the request.</span></span> <span data-ttu-id="e8970-110">L'operazione descritta in questo esempio accetta anche un parametro filename</span><span class="sxs-lookup"><span data-stu-id="e8970-110">The operation described in this example also takes a filename parameter.</span></span> <span data-ttu-id="e8970-111">che viene passato nell'URL della richiesta.</span><span class="sxs-lookup"><span data-stu-id="e8970-111">This parameter is passed within the URL of the request.</span></span> <span data-ttu-id="e8970-112">Per passare un parametro nell'URL specificare <xref:System.UriTemplate> in <xref:System.ServiceModel.Web.WebInvokeAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e8970-112">You can specify that a parameter is passed within the URL by specifying a <xref:System.UriTemplate> in the <xref:System.ServiceModel.Web.WebInvokeAttribute>.</span></span> <span data-ttu-id="e8970-113">In questo caso l'URI usato per chiamare questo metodo termina con "UploadFile/Some-filename".</span><span class="sxs-lookup"><span data-stu-id="e8970-113">In this case the URI used to call this method ends in "UploadFile/Some-Filename".</span></span> <span data-ttu-id="e8970-114">La parte "{filename}" del modello URI specifica che il parametro FileName per l'operazione viene passato all'interno dell'URI usato per chiamare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="e8970-114">The "{filename}" portion of the URI template specifies that the filename parameter for the operation is passed within the URI used to call the operation.</span></span>  
  
    ```csharp  
     [ServiceContract]  
    public interface IReceiveData  
    {  
        [WebInvoke(UriTemplate = "UploadFile/{fileName}")]  
        void UploadFile(string fileName, Stream fileContents);  
    }  
    ```  
  
2. <span data-ttu-id="e8970-115">Implementare il contratto di servizio</span><span class="sxs-lookup"><span data-stu-id="e8970-115">Implement the service contract.</span></span> <span data-ttu-id="e8970-116">Il contratto dispone di un solo metodo, `UploadFile`, che riceve un file di dati arbitrari in un flusso.</span><span class="sxs-lookup"><span data-stu-id="e8970-116">The contract has only one method, `UploadFile` that receives a file of arbitrary data in a stream.</span></span> <span data-ttu-id="e8970-117">L'operazione legge il flusso conteggiando il numero di byte letti, quindi visualizza il nome file e il numero di byte letti.</span><span class="sxs-lookup"><span data-stu-id="e8970-117">The operation reads the stream counting the number of bytes read and then displays the filename and the number of bytes read.</span></span>  
  
    ```csharp  
    public class RawDataService : IReceiveData  
    {  
        public void UploadFile(string fileName, Stream fileContents)  
        {  
            byte[] buffer = new byte[10000];  
            int bytesRead, totalBytesRead = 0;  
            do  
            {  
                bytesRead = fileContents.Read(buffer, 0, buffer.Length);  
                totalBytesRead += bytesRead;  
            } while (bytesRead > 0);  
            Console.WriteLine("Service: Received file {0} with {1} bytes", fileName, totalBytesRead);  
        }  
    }  
    ```  
  
### <a name="to-host-the-service"></a><span data-ttu-id="e8970-118">Per ospitare il servizio</span><span class="sxs-lookup"><span data-stu-id="e8970-118">To host the service</span></span>  
  
1. <span data-ttu-id="e8970-119">Creare un'applicazione console per ospitare il servizio.</span><span class="sxs-lookup"><span data-stu-id="e8970-119">Create a console application to host the service.</span></span>  
  
    ```csharp  
    class Program  
    {  
       static void Main(string[] args)  
       {  
       }  
    }  
    ```  
  
2. <span data-ttu-id="e8970-120">Creare una variabile per contenere l'indirizzo di base per il servizio all'interno del metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="e8970-120">Create a variable to hold the base address for the service within the `Main` method.</span></span>  
  
    ```csharp  
    string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
    ```  
  
3. <span data-ttu-id="e8970-121">Creare un'istanza di <xref:System.ServiceModel.ServiceHost> per il servizio che specifichi la classe del servizio e l'indirizzo di base.</span><span class="sxs-lookup"><span data-stu-id="e8970-121">Create a <xref:System.ServiceModel.ServiceHost> instance for the service that specifies the service class and the base address.</span></span>  
  
    ```csharp  
    ServiceHost host = new ServiceHost(typeof(RawDataService), new Uri(baseAddress));  
    ```  
  
4. <span data-ttu-id="e8970-122">Aggiungere un endpoint che specifichi il contratto, <xref:System.ServiceModel.WebHttpBinding> e <xref:System.ServiceModel.Description.WebHttpBehavior>.</span><span class="sxs-lookup"><span data-stu-id="e8970-122">Add an endpoint that specifies the contract, <xref:System.ServiceModel.WebHttpBinding>, and <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span>  
  
    ```csharp  
    host.AddServiceEndpoint(typeof(IReceiveData), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
    ```  
  
5. <span data-ttu-id="e8970-123">Aprire l’host del servizio.</span><span class="sxs-lookup"><span data-stu-id="e8970-123">Open the service host.</span></span> <span data-ttu-id="e8970-124">Il servizio è ora pronto a ricevere le richieste.</span><span class="sxs-lookup"><span data-stu-id="e8970-124">The service is now ready to receive requests.</span></span>  
  
    ```csharp  
    host.Open();  
    Console.WriteLine("Host opened");  
    ```  
  
### <a name="to-call-the-service-programmatically"></a><span data-ttu-id="e8970-125">Per chiamare il servizio a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="e8970-125">To call the service programmatically</span></span>  
  
1. <span data-ttu-id="e8970-126">Creare un oggetto <xref:System.Net.HttpWebRequest> con l'URI usato per chiamare il servizio.</span><span class="sxs-lookup"><span data-stu-id="e8970-126">Create a <xref:System.Net.HttpWebRequest> with the URI used to call the service.</span></span> <span data-ttu-id="e8970-127">Nel codice l'indirizzo di base è combinato con `"/UploadFile/Text"`.</span><span class="sxs-lookup"><span data-stu-id="e8970-127">In this code, the base address is combined with `"/UploadFile/Text"`.</span></span> <span data-ttu-id="e8970-128">La parte `"UploadFile"` dell'URI specifica l'operazione da chiamare.</span><span class="sxs-lookup"><span data-stu-id="e8970-128">The `"UploadFile"` portion of the URI specifies the operation to call.</span></span> <span data-ttu-id="e8970-129">La parte `"Test.txt"` dell'URI specifica il parametro filename da passare all'operazione `UploadFile`.</span><span class="sxs-lookup"><span data-stu-id="e8970-129">The `"Test.txt"` portion of the URI specifies the filename parameter to pass to the `UploadFile` operation.</span></span> <span data-ttu-id="e8970-130">Entrambi questi elementi vengono mappati all'oggetto <xref:System.UriTemplate> applicato al contratto dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="e8970-130">Both of these items map to the <xref:System.UriTemplate> applied to the operation contract.</span></span>  
  
    ```csharp  
    HttpWebRequest req = (HttpWebRequest)HttpWebRequest.Create(baseAddress + "/UploadFile/Test.txt");  
    ```  
  
2. <span data-ttu-id="e8970-131">Impostare la proprietà <xref:System.Net.HttpWebRequest.Method%2A> di <xref:System.Net.HttpWebRequest> su `POST` e la proprietà <xref:System.Net.HttpWebRequest.ContentType%2A> su `"text/plain"`.</span><span class="sxs-lookup"><span data-stu-id="e8970-131">Set the <xref:System.Net.HttpWebRequest.Method%2A> property of the <xref:System.Net.HttpWebRequest> to `POST` and the <xref:System.Net.HttpWebRequest.ContentType%2A> property to `"text/plain"`.</span></span> <span data-ttu-id="e8970-132">In questo modo si comunica al servizio che il codice sta inviando dati in formato testo normale.</span><span class="sxs-lookup"><span data-stu-id="e8970-132">This tells the service that the code is sending data and that data is in plain text.</span></span>  
  
    ```csharp  
    req.Method = "POST";  
    req.ContentType = "text/plain";  
    ```  
  
3. <span data-ttu-id="e8970-133">Chiamare <xref:System.Net.HttpWebRequest.GetRequestStream%2A> per ottenere il flusso di richiesta, creare i dati da inviare, scrivere tali dati nel flusso di richiesta e chiudere il flusso.</span><span class="sxs-lookup"><span data-stu-id="e8970-133">Call <xref:System.Net.HttpWebRequest.GetRequestStream%2A> to get the request stream, create the data to send, write that data to the request stream, and close the stream.</span></span>  
  
    ```csharp  
    Stream reqStream = req.GetRequestStream();  
    byte[] fileToSend = new byte[12345];  
    for (int i = 0; i < fileToSend.Length; i++)  
       {  
           fileToSend[i] = (byte)('a' + (i % 26));  
       }  
    reqStream.Write(fileToSend, 0, fileToSend.Length);  
    reqStream.Close();  
    ```  
  
4. <span data-ttu-id="e8970-134">Ottenere la risposta dal servizio chiamando <xref:System.Net.HttpWebRequest.GetResponse%2A> e visualizzare i dati della risposta nella console.</span><span class="sxs-lookup"><span data-stu-id="e8970-134">Get the response from the service by calling <xref:System.Net.HttpWebRequest.GetResponse%2A> and display the response data to the console.</span></span>  
  
    ```csharp  
    HttpWebResponse resp = (HttpWebResponse)req.GetResponse();  
    Console.WriteLine("Client: Receive Response HTTP/{0} {1} {2}", resp.ProtocolVersion, (int)resp.StatusCode, resp.StatusDescription);  
    ```  
  
5. <span data-ttu-id="e8970-135">Chiudere l'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="e8970-135">Close the service host.</span></span>  
  
    ```csharp  
    host.Close();  
    ```  
  
## <a name="example"></a><span data-ttu-id="e8970-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="e8970-136">Example</span></span>  
 <span data-ttu-id="e8970-137">Di seguito è riportato un elenco completo del codice per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="e8970-137">The following is a complete listing of the code for this example.</span></span>  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.ServiceModel;  
using System.ServiceModel.Web;  
using System.ServiceModel.Description;  
using System.IO;  
using System.Net;  
  
namespace ReceiveRawData  
{  
    [ServiceContract]  
    public interface IReceiveData  
    {  
        [WebInvoke(UriTemplate = "UploadFile/{fileName}")]  
        void UploadFile(string fileName, Stream fileContents);  
    }  
    public class RawDataService : IReceiveData  
    {  
        public void UploadFile(string fileName, Stream fileContents)  
        {  
            byte[] buffer = new byte[10000];  
            int bytesRead, totalBytesRead = 0;  
            do  
            {  
                bytesRead = fileContents.Read(buffer, 0, buffer.Length);  
                totalBytesRead += bytesRead;  
            } while (bytesRead > 0);  
            Console.WriteLine("Service: Received file {0} with {1} bytes", fileName, totalBytesRead);  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
            ServiceHost host = new ServiceHost(typeof(RawDataService), new Uri(baseAddress));  
            host.AddServiceEndpoint(typeof(IReceiveData), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
            host.Open();  
            Console.WriteLine("Host opened");  
  
            HttpWebRequest req = (HttpWebRequest)HttpWebRequest.Create(baseAddress + "/UploadFile/Test.txt");  
            req.Method = "POST";  
            req.ContentType = "text/plain";  
            Stream reqStream = req.GetRequestStream();  
            byte[] fileToSend = new byte[12345];  
            for (int i = 0; i < fileToSend.Length; i++)  
            {  
                fileToSend[i] = (byte)('a' + (i % 26));  
            }  
            reqStream.Write(fileToSend, 0, fileToSend.Length);  
            reqStream.Close();  
            HttpWebResponse resp = (HttpWebResponse)req.GetResponse();  
            Console.WriteLine("Client: Receive Response HTTP/{0} {1} {2}", resp.ProtocolVersion, (int)resp.StatusCode, resp.StatusDescription);  
            host.Close();  
  
        }  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e8970-138">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="e8970-138">Compiling the Code</span></span>  
  
- <span data-ttu-id="e8970-139">Durante la compilazione del codice, fare riferimento a System.ServiceModel.dll e System.ServiceModel.Web.dll.</span><span class="sxs-lookup"><span data-stu-id="e8970-139">When compiling the code reference System.ServiceModel.dll and System.ServiceModel.Web.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8970-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8970-140">See also</span></span>

- [<span data-ttu-id="e8970-141">UriTemplate e UriTemplateTable</span><span class="sxs-lookup"><span data-stu-id="e8970-141">UriTemplate and UriTemplateTable</span></span>](uritemplate-and-uritemplatetable.md)
- [<span data-ttu-id="e8970-142">Modello di programmazione HTTP Web WCF</span><span class="sxs-lookup"><span data-stu-id="e8970-142">WCF Web HTTP Programming Model</span></span>](wcf-web-http-programming-model.md)
- [<span data-ttu-id="e8970-143">Panoramica sul modello di programmazione HTTP Web WCF</span><span class="sxs-lookup"><span data-stu-id="e8970-143">WCF Web HTTP Programming Model Overview</span></span>](wcf-web-http-programming-model-overview.md)
