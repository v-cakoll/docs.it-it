---
title: Creazione di richieste Internet
description: Informazioni su come le applicazioni creano istanze di WebRequest tramite il metodo WebRequest. Create, che crea una classe derivata basata sullo schema URI passato.
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
ms.openlocfilehash: 389c7bf5969eca4322aa680a6f28dec0b899709a
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325640"
---
# <a name="create-internet-requests"></a><span data-ttu-id="2e35e-103">Creare richieste Internet</span><span class="sxs-lookup"><span data-stu-id="2e35e-103">Create internet requests</span></span>

<span data-ttu-id="2e35e-104">Le applicazioni creano istanze di <xref:System.Net.WebRequest> con il metodo <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2e35e-104">Applications create <xref:System.Net.WebRequest> instances through the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="2e35e-105"><xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType>è un metodo statico che crea una classe derivata da <xref:System.Net.WebRequest> in base allo schema URI passato.</span><span class="sxs-lookup"><span data-stu-id="2e35e-105"><xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> is a static method that creates a class derived from <xref:System.Net.WebRequest> based on the URI scheme passed to it.</span></span>  
  
## <a name="web-file-and-ftp-requests"></a><span data-ttu-id="2e35e-106">Richieste Web, file e FTP</span><span class="sxs-lookup"><span data-stu-id="2e35e-106">Web, file, and FTP requests</span></span>

<span data-ttu-id="2e35e-107">.NET Framework fornisce la <xref:System.Net.HttpWebRequest> classe, derivata da `WebRequest` , per gestire le richieste HTTP e HTTPS.</span><span class="sxs-lookup"><span data-stu-id="2e35e-107">.NET Framework provides the <xref:System.Net.HttpWebRequest> class, which is derived from `WebRequest`, to handle HTTP and HTTPS requests.</span></span> <span data-ttu-id="2e35e-108">Nella maggior parte dei casi, la `WebRequest` classe fornisce tutte le proprietà necessarie per effettuare una richiesta. Tuttavia, se necessario, è possibile eseguire il cast di `WebRequest` oggetti creati dal `WebRequest.Create` metodo al `HttpWebRequest` tipo per accedere alle proprietà specifiche di http della richiesta.</span><span class="sxs-lookup"><span data-stu-id="2e35e-108">In most cases, the `WebRequest` class provides all the properties you need to make a request; however, if necessary, you can cast `WebRequest` objects created by the `WebRequest.Create` method to the `HttpWebRequest` type to access the HTTP-specific properties of the request.</span></span> <span data-ttu-id="2e35e-109">Analogamente, l' `HttpWebResponse` oggetto gestisce le risposte dalle richieste HTTP e HTTPS.</span><span class="sxs-lookup"><span data-stu-id="2e35e-109">Similarly, the `HttpWebResponse` object handles the responses from HTTP and HTTPS requests.</span></span> <span data-ttu-id="2e35e-110">Per accedere alle proprietà specifiche di HTTP dell' `HttpWebResponse` oggetto, è necessario eseguire il cast `WebResponse` degli oggetti al `HttpWebResponse` tipo.</span><span class="sxs-lookup"><span data-stu-id="2e35e-110">To access the HTTP-specific properties of the `HttpWebResponse` object, you need to cast `WebResponse` objects to the `HttpWebResponse` type.</span></span>  
  
<span data-ttu-id="2e35e-111">.NET Framework fornisce anche le <xref:System.Net.FileWebRequest> <xref:System.Net.FileWebResponse> classi e per gestire le richieste di risorse che usano lo schema URI "file:".</span><span class="sxs-lookup"><span data-stu-id="2e35e-111">.NET Framework also provides the <xref:System.Net.FileWebRequest> and <xref:System.Net.FileWebResponse> classes to handle requests for resources that use the "file:" URI scheme.</span></span> <span data-ttu-id="2e35e-112">Analogamente, sono disponibili le classi <xref:System.Net.FtpWebRequest> e <xref:System.Net.FtpWebResponse> per la gestione delle richieste di risorse che usano lo schema "ftp:".</span><span class="sxs-lookup"><span data-stu-id="2e35e-112">Likewise, the <xref:System.Net.FtpWebRequest> and <xref:System.Net.FtpWebResponse> classes are provided to handle requests for resources that use the "ftp:" scheme.</span></span> <span data-ttu-id="2e35e-113">Se la richiesta riguarda una risorsa che usa uno di questi schemi, è possibile usare il `WebRequest.Create` metodo per ottenere un oggetto con cui eseguire la richiesta.</span><span class="sxs-lookup"><span data-stu-id="2e35e-113">If your request is for a resource that uses any of these schemes, you can use the `WebRequest.Create` method to obtain an object with which to make your request.</span></span>  
  
<span data-ttu-id="2e35e-114">Per gestire le richieste che usano altri protocolli a livello di applicazione, implementare classi specifiche del protocollo derivate da `WebRequest` e `WebResponse` .</span><span class="sxs-lookup"><span data-stu-id="2e35e-114">To handle requests that use other application-level protocols, implement protocol-specific classes derived from `WebRequest` and `WebResponse`.</span></span> <span data-ttu-id="2e35e-115">Per ulteriori informazioni, vedere [programmazione di protocolli di collegamento](programming-pluggable-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="2e35e-115">For more information, see [Programming Pluggable Protocols](programming-pluggable-protocols.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e35e-116">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="2e35e-116">See also</span></span>

- [<span data-ttu-id="2e35e-117">Procedura: Richiedere dati con la classe WebRequest</span><span class="sxs-lookup"><span data-stu-id="2e35e-117">How to: Request Data Using the WebRequest Class</span></span>](how-to-request-data-using-the-webrequest-class.md)
- [<span data-ttu-id="2e35e-118">Richiesta di dati</span><span class="sxs-lookup"><span data-stu-id="2e35e-118">Requesting Data</span></span>](requesting-data.md)
