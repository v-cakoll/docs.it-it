---
title: FTP
ms.date: 03/30/2017
helpviewer_keywords:
- FTP
ms.assetid: 9b43f8b4-89d7-46a7-89fc-71aca916dd32
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: e5dc6ee0f2c832e3274a1e58808acfdb56ae804c
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43862978"
---
# <a name="ftp"></a><span data-ttu-id="bf87f-102">FTP</span><span class="sxs-lookup"><span data-stu-id="bf87f-102">FTP</span></span>
<span data-ttu-id="bf87f-103">.NET Framework offre supporto completo per il protocollo FTP con le classi <xref:System.Net.FtpWebRequest> e <xref:System.Net.FtpWebResponse>.</span><span class="sxs-lookup"><span data-stu-id="bf87f-103">The .NET Framework provides comprehensive support for the FTP protocol with the <xref:System.Net.FtpWebRequest> and <xref:System.Net.FtpWebResponse> classes.</span></span> <span data-ttu-id="bf87f-104">Queste classi sono derivate da <xref:System.Net.WebRequest> e <xref:System.Net.WebResponse>.</span><span class="sxs-lookup"><span data-stu-id="bf87f-104">These classes are derived from <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="bf87f-105">Nella maggior parte dei casi, le classi <xref:System.Net.WebRequest> e <xref:System.Net.WebResponse> rendono disponibile tutto ciò che serve per eseguire la richiesta. Se tuttavia è necessario accedere alle funzionalità specifiche di FTP esposte come proprietà, è possibile eseguire il cast di tipo di queste classi a <xref:System.Net.FtpWebRequest> o <xref:System.Net.FtpWebResponse>.</span><span class="sxs-lookup"><span data-stu-id="bf87f-105">In most cases, the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes provide all that is necessary to make the request, but if you need access to the FTP-specific features exposed as properties, you can typecast these classes to <xref:System.Net.FtpWebRequest> or <xref:System.Net.FtpWebResponse>.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="bf87f-106">Esempi</span><span class="sxs-lookup"><span data-stu-id="bf87f-106">Examples</span></span>  
 <span data-ttu-id="bf87f-107">Per altre informazioni, vedere gli argomenti seguenti: [Procedura: Scaricare file con FTP](../../../docs/framework/network-programming/how-to-download-files-with-ftp.md), [Procedura: Caricare file con FTP](../../../docs/framework/network-programming/how-to-upload-files-with-ftp.md), e [Procedura: Elencare il contenuto della directory con FTP](../../../docs/framework/network-programming/how-to-list-directory-contents-with-ftp.md).</span><span class="sxs-lookup"><span data-stu-id="bf87f-107">For more information, see the following topics: [How to: Download Files with FTP](../../../docs/framework/network-programming/how-to-download-files-with-ftp.md), [How to: Upload Files with FTP](../../../docs/framework/network-programming/how-to-upload-files-with-ftp.md), and [How to: List Directory Contents with FTP](../../../docs/framework/network-programming/how-to-list-directory-contents-with-ftp.md).</span></span>  
  
## <a name="ftp-and-proxies"></a><span data-ttu-id="bf87f-108">FTP e proxy</span><span class="sxs-lookup"><span data-stu-id="bf87f-108">FTP and proxies</span></span>  
 <span data-ttu-id="bf87f-109">Se un proxy (specificato dalla proprietà <xref:System.Net.FtpWebRequest.Proxy%2A>) è un proxy HTTP, sono supportati solo i comandi <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory> e <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails>.</span><span class="sxs-lookup"><span data-stu-id="bf87f-109">If a proxy (specified by the <xref:System.Net.FtpWebRequest.Proxy%2A> property) is an HTTP proxy, then only the <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory>, and <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails> commands are supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf87f-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf87f-110">See Also</span></span>  
 [<span data-ttu-id="bf87f-111">Accesso a Internet con un proxy</span><span class="sxs-lookup"><span data-stu-id="bf87f-111">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [<span data-ttu-id="bf87f-112">Esempi di programmazione di rete</span><span class="sxs-lookup"><span data-stu-id="bf87f-112">Network Programming Samples</span></span>](../../../docs/framework/network-programming/network-programming-samples.md)  
 <span data-ttu-id="bf87f-113">[FTP Client Technology Sample](https://go.microsoft.com/fwlink/?LinkID=179557) (Esempio di tecnologia client FTP)</span><span class="sxs-lookup"><span data-stu-id="bf87f-113">[FTP Client Technology Sample](https://go.microsoft.com/fwlink/?LinkID=179557)</span></span>  
 <span data-ttu-id="bf87f-114">[FTP Explorer Technology Sample](https://go.microsoft.com/fwlink/?LinkID=179569) (Esempio di tecnologia esplora risorse FTP)</span><span class="sxs-lookup"><span data-stu-id="bf87f-114">[FTP Explorer Technology Sample](https://go.microsoft.com/fwlink/?LinkID=179569)</span></span>  
 [<span data-ttu-id="bf87f-115">Uso di protocolli applicativi</span><span class="sxs-lookup"><span data-stu-id="bf87f-115">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)
