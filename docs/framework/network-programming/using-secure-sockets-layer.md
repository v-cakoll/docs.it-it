---
title: Uso di Secure Sockets Layer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Networking
- SSL
- Secure Sockets Layer
- requesting data from Internet, Secure Sockets Layer
- sending data, Secure Sockets Layer
- Network Resources
- data requests, Secure Sockets Layer
- receiving data, Secure Sockets Layer
- Internet, Secure Sockets Layer
ms.assetid: 6e4289e6-d1b7-4e82-ab0d-e83e3b6063ed
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 77f115afab9c0ad4b53a38d8cdb3683616738b1d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="using-secure-sockets-layer"></a><span data-ttu-id="135b7-102">Uso di Secure Sockets Layer</span><span class="sxs-lookup"><span data-stu-id="135b7-102">Using Secure Sockets Layer</span></span>
<span data-ttu-id="135b7-103">Le classi <xref:System.Net> usano Secure Sockets Layer (SSL) per crittografare la connessione per diversi protocolli di rete.</span><span class="sxs-lookup"><span data-stu-id="135b7-103">The <xref:System.Net> classes use the Secure Sockets Layer (SSL) to encrypt the connection for several network protocols.</span></span>  
  
 <span data-ttu-id="135b7-104">Per le connessioni HTTP, le classi <xref:System.Net.WebRequest> e <xref:System.Net.WebResponse> usano SSL per comunicare con host Web che supportano SSL.</span><span class="sxs-lookup"><span data-stu-id="135b7-104">For http connections, the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes use SSL to communicate with web hosts that support SSL.</span></span> <span data-ttu-id="135b7-105">La decisione di usare SSL avviene tramite la classe <xref:System.Net.WebRequest>, in base all'URI assegnato.</span><span class="sxs-lookup"><span data-stu-id="135b7-105">The decision to use SSL is made by the <xref:System.Net.WebRequest> class, based on the URI it is given.</span></span> <span data-ttu-id="135b7-106">Se l'URI inizia con "https:", viene usato SSL. Se l'URI inizia con "http:", viene usata una connessione non crittografata.</span><span class="sxs-lookup"><span data-stu-id="135b7-106">If the URI begins with "https:", SSL is used; if the URI begins with "http:", an unencrypted connection is used.</span></span>  
  
 <span data-ttu-id="135b7-107">Per usare SSL con FTP (File Transfer Protocol), impostare la proprietà <xref:System.Net.FtpWebRequest.EnableSsl> su true prima di chiamare <xref:System.Net.FtpWebRequest.GetResponse>.</span><span class="sxs-lookup"><span data-stu-id="135b7-107">To use SSL with File Transfer Protocol (FTP), set the <xref:System.Net.FtpWebRequest.EnableSsl> property to true prior to calling <xref:System.Net.FtpWebRequest.GetResponse>.</span></span> <span data-ttu-id="135b7-108">Analogamente, per usare SSL con SMTP (Simple Mail Transport Protocol), impostare la proprietà <xref:System.Net.Mail.SmtpClient.EnableSsl> su true prima di inviare messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="135b7-108">Similarly, to use SSL with Simple Mail Transport Protocol (SMTP), set the <xref:System.Net.Mail.SmtpClient.EnableSsl> property to true prior to sending the e-mail.</span></span>  
  
 <span data-ttu-id="135b7-109">La classe <xref:System.Net.Security.SslStream> fornisce un'astrazione basata su flussi per SSL e offre diversi modi per configurare l'handshake SSL.</span><span class="sxs-lookup"><span data-stu-id="135b7-109">The <xref:System.Net.Security.SslStream> class provides a stream-based abstraction for SSL, and offers many ways to configure the SSL handshake.</span></span>  
  
## <a name="example"></a><span data-ttu-id="135b7-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="135b7-110">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="135b7-111">Codice</span><span class="sxs-lookup"><span data-stu-id="135b7-111">Code</span></span>  
  
```vb  
Dim MyURI As String = "https://www.contoso.com/"  
Dim Wreq As WebRequest = WebRequest.Create(MyURI)  
  
Dim serverUri As String = "ftp://ftp.contoso.com/file.txt"  
Dim request As FtpWebRequest = CType(WebRequest.Create(serverUri), FtpWebRequest)  
request.Method = WebRequestMethods.Ftp.DeleteFile  
request.EnableSsl = True  
Dim response As FtpWebResponse = CType(request.GetResponse(), FtpWebResponse)  
```  
  
```csharp  
String MyURI = "https://www.contoso.com/";  
WebRequest WReq = WebRequest.Create(MyURI);  
  
String serverUri = "ftp://ftp.contoso.com/file.txt"  
FtpWebRequest request = (FtpWebRequest)WebRequest.Create(serverUri);  
request.EnableSsl = true;  
request.Method = WebRequestMethods.Ftp.DeleteFile;  
FtpWebResponse response = (FtpWebResponse)request.GetResponse();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="135b7-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="135b7-112">Compiling the Code</span></span>  
 <span data-ttu-id="135b7-113">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="135b7-113">This example requires:</span></span>  
  
-   <span data-ttu-id="135b7-114">Riferimenti allo spazio dei nomi **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="135b7-114">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="135b7-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="135b7-115">See Also</span></span>  
 [<span data-ttu-id="135b7-116">Sicurezza nella programmazione di rete</span><span class="sxs-lookup"><span data-stu-id="135b7-116">Security in Network Programming</span></span>](../../../docs/framework/network-programming/security-in-network-programming.md)  
 [<span data-ttu-id="135b7-117">Programmazione di rete in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="135b7-117">Network Programming in the .NET Framework</span></span>](../../../docs/framework/network-programming/index.md)  
 [<span data-ttu-id="135b7-118">Selezione e convalida dei certificati</span><span class="sxs-lookup"><span data-stu-id="135b7-118">Certificate Selection and Validation</span></span>](../../../docs/framework/network-programming/certificate-selection-and-validation.md)
