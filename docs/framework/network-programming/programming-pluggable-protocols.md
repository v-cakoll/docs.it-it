---
title: programmazione di protocolli di collegamento
description: Informazioni su come le classi astratte WebRequest e WebResponse supportano i protocolli di collegamento, che consentono a un'applicazione di ottenere i dati senza specificare un protocollo.
ms.date: 03/30/2017
helpviewer_keywords:
- downloading Internet resources, pluggable protocols
- WebRequest class, pluggable protocols
- response to Internet request, pluggable protocols
- WebResponse class, pluggable protocols
- sending data, pluggable protocols
- network resources, pluggable protocols
- Internet, pluggable protocols
- programming pluggable protocols
- pluggable protocols, programming
- requesting data from Internet, pluggable protocols
- receiving data, pluggable protocols
- protocols, pluggable
ms.assetid: 66ef8456-7576-4e97-8956-959b216373db
ms.openlocfilehash: 510f616295abc13d93e0e0af5a37aca097d343e3
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502197"
---
# <a name="programming-pluggable-protocols"></a><span data-ttu-id="28def-103">programmazione di protocolli di collegamento</span><span class="sxs-lookup"><span data-stu-id="28def-103">Programming Pluggable Protocols</span></span>
<span data-ttu-id="28def-104">Le classi astratte <xref:System.Net.WebRequest> e <xref:System.Net.WebResponse> rappresentano la base per i protocolli di collegamento.</span><span class="sxs-lookup"><span data-stu-id="28def-104">The abstract <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes provide the base for pluggable protocols.</span></span> <span data-ttu-id="28def-105">Tramite la derivazione di classi specifiche del protocollo da <xref:System.Net.WebRequest> e <xref:System.Net.WebResponse>, un'applicazione può richiedere i dati da una risorsa Internet e leggere la risposta senza specificare il protocollo usato.</span><span class="sxs-lookup"><span data-stu-id="28def-105">By deriving protocol-specific classes from <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse>, an application can request data from an Internet resource and read the response without specifying the protocol being used.</span></span>  
  
 <span data-ttu-id="28def-106">Prima di poter creare una <xref:System.Net.WebRequest> specifica del protocollo, è necessario registrarne il metodo Create.</span><span class="sxs-lookup"><span data-stu-id="28def-106">Before you can create a protocol-specific <xref:System.Net.WebRequest>, you must register its Create method.</span></span> <span data-ttu-id="28def-107">Usare il metodo statico <xref:System.Net.WebRequest.RegisterPrefix%28System.String%2CSystem.Net.IWebRequestCreate%29> di <xref:System.Net.WebRequest> per registrare un discendente <xref:System.Net.WebRequest> per la gestione di un set di richieste in un particolare schema Internet, in uno schema e un server oppure in uno schema, un server e un percorso.</span><span class="sxs-lookup"><span data-stu-id="28def-107">Use the static <xref:System.Net.WebRequest.RegisterPrefix%28System.String%2CSystem.Net.IWebRequestCreate%29> method of <xref:System.Net.WebRequest> to register a <xref:System.Net.WebRequest> descendant to handle a set of requests to a particular Internet scheme, to a scheme and server, or to a scheme, server, and path.</span></span>  
  
 <span data-ttu-id="28def-108">Nella maggior parte dei casi sarà possibile inviare e ricevere dati tramite i metodi e le proprietà della classe <xref:System.Net.WebRequest>.</span><span class="sxs-lookup"><span data-stu-id="28def-108">In most cases you will be able to send and receive data using the methods and properties of the <xref:System.Net.WebRequest> class.</span></span> <span data-ttu-id="28def-109">Tuttavia, se è necessario accedere alle proprietà specifiche del protocollo, è possibile eseguire il cast di tipo di <xref:System.Net.WebRequest> su una specifica istanza della classe derivata.</span><span class="sxs-lookup"><span data-stu-id="28def-109">However, if you need to access protocol-specific properties, you can typecast a <xref:System.Net.WebRequest> to a specific derived-class instance.</span></span>  
  
 <span data-ttu-id="28def-110">Per sfruttare i protocolli di collegamento, i discendenti <xref:System.Net.WebRequest> devono fornire una transazione di richiesta e risposta predefinita che non richiede l'impostazione di proprietà specifiche del protocollo.</span><span class="sxs-lookup"><span data-stu-id="28def-110">To take advantage of pluggable protocols, your <xref:System.Net.WebRequest> descendants must provide a default request-and-response transaction that does not require protocol-specific properties to be set.</span></span> <span data-ttu-id="28def-111">Ad esempio, la classe <xref:System.Net.HttpWebRequest> che implementa la classe <xref:System.Net.WebRequest> per il protocollo HTTP, fornisce una richiesta `GET` per impostazione predefinita e restituisce una <xref:System.Net.HttpWebResponse> che contiene il flusso restituito dal server Web.</span><span class="sxs-lookup"><span data-stu-id="28def-111">For example, the <xref:System.Net.HttpWebRequest> class, which implements the <xref:System.Net.WebRequest> class for HTTP, provides a `GET` request by default and returns an <xref:System.Net.HttpWebResponse> that contains the stream returned from the Web server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28def-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28def-112">See also</span></span>

- [<span data-ttu-id="28def-113">Derivazione da WebRequest</span><span class="sxs-lookup"><span data-stu-id="28def-113">Deriving from WebRequest</span></span>](deriving-from-webrequest.md)
- [<span data-ttu-id="28def-114">Derivazione da WebResponse</span><span class="sxs-lookup"><span data-stu-id="28def-114">Deriving from WebResponse</span></span>](deriving-from-webresponse.md)
- [<span data-ttu-id="28def-115">Programmazione di rete nel .NET Framework</span><span class="sxs-lookup"><span data-stu-id="28def-115">Network Programming in the .NET Framework</span></span>](index.md)
- [<span data-ttu-id="28def-116">Procedura: Eseguire il cast di tipo di un oggetto WebRequest per accedere a proprietà specifiche del protocollo</span><span class="sxs-lookup"><span data-stu-id="28def-116">How to: Typecast a WebRequest to Access Protocol Specific Properties</span></span>](how-to-typecast-a-webrequest-to-access-protocol-specific-properties.md)
