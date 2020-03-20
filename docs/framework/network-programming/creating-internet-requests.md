---
title: Creazione di richieste Internet
ms.date: 03/30/2017
helpviewer_keywords:
- WebRequest class, sending and receiving data
- Networking
- HttpWebResponse class, sending and receiving data
- requesting data from Internet, creating requests
- Network Resources
- Internet, requesting data
- data requests, creating requests
ms.assetid: faab683e-3f1e-4eee-b5e9-59f7245033d5
ms.openlocfilehash: 80e3a6bd199691df9391e88d5a64fab5df2a08a1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048613"
---
# <a name="creating-internet-requests"></a><span data-ttu-id="14f31-102">Creazione di richieste Internet</span><span class="sxs-lookup"><span data-stu-id="14f31-102">Creating Internet Requests</span></span>
<span data-ttu-id="14f31-103">Le applicazioni creano istanze di <xref:System.Net.WebRequest> con il metodo <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="14f31-103">Applications create <xref:System.Net.WebRequest> instances through the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="14f31-104">Questo è un metodo statico che crea una classe derivata da **WebRequest** in base allo schema URI passato.</span><span class="sxs-lookup"><span data-stu-id="14f31-104">This is a static method that creates a class derived from **WebRequest** based on the URI scheme passed to it.</span></span>  
  
## <a name="web-file-and-ftp-requests"></a><span data-ttu-id="14f31-105">Web, file e richieste FTP</span><span class="sxs-lookup"><span data-stu-id="14f31-105">Web, File and FTP Requests</span></span>  
 <span data-ttu-id="14f31-106">.NET Framework contiene la classe <xref:System.Net.HttpWebRequest>, derivata da **WebRequest**, per gestire richieste HTTP e HTTPS.</span><span class="sxs-lookup"><span data-stu-id="14f31-106">The .NET Framework provides the <xref:System.Net.HttpWebRequest> class, which is derived from **WebRequest**, to handle HTTP and HTTPS requests.</span></span> <span data-ttu-id="14f31-107">Nella maggior parte dei casi, la classe **WebRequest** fornisce tutte le proprietà necessarie per effettuare una richiesta. Se necessario, tuttavia, è possibile eseguire il cast degli oggetti **WebRequest** creati dal metodo **WebRequest.Create** al tipo **HttpWebRequest** per accedere alle proprietà specifiche di HTTP della richiesta.</span><span class="sxs-lookup"><span data-stu-id="14f31-107">In most cases, the **WebRequest** class provides all the properties you need to make a request; however, if necessary, you can cast **WebRequest** objects created by the **WebRequest.Create** method to the **HttpWebRequest** type to access the HTTP-specific properties of the request.</span></span> <span data-ttu-id="14f31-108">Analogamente, l'oggetto **HttpWebResponse** gestisce le risposte alle richieste provenienti da HTTP e da HTTPS.</span><span class="sxs-lookup"><span data-stu-id="14f31-108">Similarly, the **HttpWebResponse** object handles the responses from HTTP and HTTPS requests.</span></span> <span data-ttu-id="14f31-109">Per accedere alle proprietà specifiche di HTTP dell'oggetto **HttpWebResponse**, è necessario eseguire il cast degli oggetti **WebResponse** al tipo **HttpWebResponse**.</span><span class="sxs-lookup"><span data-stu-id="14f31-109">To access the HTTP-specific properties of the **HttpWebResponse** object, you need to cast **WebResponse** objects to the **HttpWebResponse** type.</span></span>  
  
 <span data-ttu-id="14f31-110">.NET Framework mette a disposizione anche le classi <xref:System.Net.FileWebRequest> e <xref:System.Net.FileWebResponse> per la gestione delle richieste di risorse che usano lo schema URI "file:".</span><span class="sxs-lookup"><span data-stu-id="14f31-110">The .NET Framework also provides the <xref:System.Net.FileWebRequest> and <xref:System.Net.FileWebResponse> classes to handle requests for resources that use the "file:" URI scheme.</span></span> <span data-ttu-id="14f31-111">Analogamente, sono disponibili le classi <xref:System.Net.FtpWebRequest> e <xref:System.Net.FtpWebResponse> per la gestione delle richieste di risorse che usano lo schema "ftp:".</span><span class="sxs-lookup"><span data-stu-id="14f31-111">Likewise, the <xref:System.Net.FtpWebRequest> and <xref:System.Net.FtpWebResponse> classes are provided to handle requests for resources that use the "ftp:" scheme.</span></span> <span data-ttu-id="14f31-112">Se la richiesta riguarda una risorsa che usa uno di questi schemi, è possibile usare il metodo **WebRequest** per ottenere un oggetto con cui effettuare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="14f31-112">If your request is for a resource that uses any of these schemes, you can use the **WebRequest.Create** method to obtain an object with which to make your request.</span></span>  
  
 <span data-ttu-id="14f31-113">Per gestire le richieste che usano altri protocolli a livello di applicazione, è necessario implementare classi specifiche del protocollo derivate da **WebRequest** e **WebResponse**.</span><span class="sxs-lookup"><span data-stu-id="14f31-113">To handle requests that use other application-level protocols, you need to implement protocol-specific classes derived from **WebRequest** and **WebResponse**.</span></span> <span data-ttu-id="14f31-114">Per ulteriori informazioni, vedere [Programmazione di protocolli collegabili](programming-pluggable-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="14f31-114">For more information, see [Programming Pluggable Protocols](programming-pluggable-protocols.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14f31-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14f31-115">See also</span></span>

- [<span data-ttu-id="14f31-116">Procedura: Richiedere dati con la classe WebRequest</span><span class="sxs-lookup"><span data-stu-id="14f31-116">How to: Request Data Using the WebRequest Class</span></span>](how-to-request-data-using-the-webrequest-class.md)
- [<span data-ttu-id="14f31-117">Richiesta di dati</span><span class="sxs-lookup"><span data-stu-id="14f31-117">Requesting Data</span></span>](requesting-data.md)
