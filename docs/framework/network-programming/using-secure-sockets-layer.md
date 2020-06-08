---
title: Uso di Secure Sockets Layer
description: Informazioni sul modo in cui System.Net ed estensione delle classi usano la Secure Sockets Layer per crittografare la connessione per diversi protocolli di rete nel .NET Framework.
ms.date: 03/30/2017
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
ms.openlocfilehash: 67330962382e768849cbf67d5f412ea80f65569d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501989"
---
# <a name="using-secure-sockets-layer"></a><span data-ttu-id="a3c67-103">Uso di Secure Sockets Layer</span><span class="sxs-lookup"><span data-stu-id="a3c67-103">Using Secure Sockets Layer</span></span>
<span data-ttu-id="a3c67-104">Le classi <xref:System.Net> usano Secure Sockets Layer (SSL) per crittografare la connessione per diversi protocolli di rete.</span><span class="sxs-lookup"><span data-stu-id="a3c67-104">The <xref:System.Net> classes use the Secure Sockets Layer (SSL) to encrypt the connection for several network protocols.</span></span>  
  
 <span data-ttu-id="a3c67-105">Per le connessioni HTTP, le classi <xref:System.Net.WebRequest> e <xref:System.Net.WebResponse> usano SSL per comunicare con host Web che supportano SSL.</span><span class="sxs-lookup"><span data-stu-id="a3c67-105">For http connections, the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes use SSL to communicate with web hosts that support SSL.</span></span> <span data-ttu-id="a3c67-106">La decisione di usare SSL avviene tramite la classe <xref:System.Net.WebRequest>, in base all'URI assegnato.</span><span class="sxs-lookup"><span data-stu-id="a3c67-106">The decision to use SSL is made by the <xref:System.Net.WebRequest> class, based on the URI it is given.</span></span> <span data-ttu-id="a3c67-107">Se l'URI inizia con "https:", viene usato SSL. Se l'URI inizia con "http:", viene usata una connessione non crittografata.</span><span class="sxs-lookup"><span data-stu-id="a3c67-107">If the URI begins with "https:", SSL is used; if the URI begins with "http:", an unencrypted connection is used.</span></span>  
  
 <span data-ttu-id="a3c67-108">Per usare SSL con FTP (File Transfer Protocol), impostare la proprietà <xref:System.Net.FtpWebRequest.EnableSsl> su true prima di chiamare <xref:System.Net.FtpWebRequest.GetResponse>.</span><span class="sxs-lookup"><span data-stu-id="a3c67-108">To use SSL with File Transfer Protocol (FTP), set the <xref:System.Net.FtpWebRequest.EnableSsl> property to true prior to calling <xref:System.Net.FtpWebRequest.GetResponse>.</span></span> <span data-ttu-id="a3c67-109">Analogamente, per usare SSL con SMTP (Simple Mail Transport Protocol), impostare la proprietà <xref:System.Net.Mail.SmtpClient.EnableSsl> su true prima di inviare messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="a3c67-109">Similarly, to use SSL with Simple Mail Transport Protocol (SMTP), set the <xref:System.Net.Mail.SmtpClient.EnableSsl> property to true prior to sending the email.</span></span>  
  
 <span data-ttu-id="a3c67-110">La classe <xref:System.Net.Security.SslStream> fornisce un'astrazione basata su flussi per SSL e offre diversi modi per configurare l'handshake SSL.</span><span class="sxs-lookup"><span data-stu-id="a3c67-110">The <xref:System.Net.Security.SslStream> class provides a stream-based abstraction for SSL, and offers many ways to configure the SSL handshake.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3c67-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="a3c67-111">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="a3c67-112">Codice</span><span class="sxs-lookup"><span data-stu-id="a3c67-112">Code</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="a3c67-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="a3c67-113">Compiling the Code</span></span>  
 <span data-ttu-id="a3c67-114">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a3c67-114">This example requires:</span></span>  
  
- <span data-ttu-id="a3c67-115">Riferimenti allo spazio dei nomi **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="a3c67-115">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3c67-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3c67-116">See also</span></span>

- [<span data-ttu-id="a3c67-117">Sicurezza nella programmazione di rete</span><span class="sxs-lookup"><span data-stu-id="a3c67-117">Security in Network Programming</span></span>](security-in-network-programming.md)
- [<span data-ttu-id="a3c67-118">Programmazione di rete nel .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a3c67-118">Network Programming in the .NET Framework</span></span>](index.md)
- [<span data-ttu-id="a3c67-119">Selezione e convalida dei certificati</span><span class="sxs-lookup"><span data-stu-id="a3c67-119">Certificate Selection and Validation</span></span>](certificate-selection-and-validation.md)
