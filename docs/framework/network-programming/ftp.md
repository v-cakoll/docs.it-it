---
title: FTP - .NET
description: Informazioni sul supporto completo per il protocollo FTP fornito dal .NET Framework tramite le classi FtpWebRequest e FtpWebResponse.
ms.date: 03/30/2017
helpviewer_keywords:
- FTP
ms.assetid: 9b43f8b4-89d7-46a7-89fc-71aca916dd32
ms.openlocfilehash: d21ca43cd1041df358dc5e2add9560fb33e85d83
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502587"
---
# <a name="ftp"></a><span data-ttu-id="5a98c-103">FTP</span><span class="sxs-lookup"><span data-stu-id="5a98c-103">FTP</span></span>

<span data-ttu-id="5a98c-104">.NET Framework offre supporto completo per il protocollo FTP con le classi <xref:System.Net.FtpWebRequest> e <xref:System.Net.FtpWebResponse>.</span><span class="sxs-lookup"><span data-stu-id="5a98c-104">The .NET Framework provides comprehensive support for the FTP protocol with the <xref:System.Net.FtpWebRequest> and <xref:System.Net.FtpWebResponse> classes.</span></span> <span data-ttu-id="5a98c-105">Queste classi sono derivate da <xref:System.Net.WebRequest> e <xref:System.Net.WebResponse>.</span><span class="sxs-lookup"><span data-stu-id="5a98c-105">These classes are derived from <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="5a98c-106">Nella maggior parte dei casi, le classi <xref:System.Net.WebRequest> e <xref:System.Net.WebResponse> rendono disponibile tutto ciò che serve per eseguire la richiesta. Se tuttavia è necessario accedere alle funzionalità specifiche di FTP esposte come proprietà, è possibile eseguire il cast di tipo di queste classi a <xref:System.Net.FtpWebRequest> o <xref:System.Net.FtpWebResponse>.</span><span class="sxs-lookup"><span data-stu-id="5a98c-106">In most cases, the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes provide all that is necessary to make the request, but if you need access to the FTP-specific features exposed as properties, you can typecast these classes to <xref:System.Net.FtpWebRequest> or <xref:System.Net.FtpWebResponse>.</span></span>

## <a name="examples"></a><span data-ttu-id="5a98c-107">Esempi</span><span class="sxs-lookup"><span data-stu-id="5a98c-107">Examples</span></span>

<span data-ttu-id="5a98c-108">Per altre informazioni, vedere gli argomenti seguenti: [Procedura: Scaricare file con FTP](how-to-download-files-with-ftp.md), [Procedura: Caricare file con FTP](how-to-upload-files-with-ftp.md), e [Procedura: Elencare il contenuto della directory con FTP](how-to-list-directory-contents-with-ftp.md).</span><span class="sxs-lookup"><span data-stu-id="5a98c-108">For more information, see the following topics: [How to: Download Files with FTP](how-to-download-files-with-ftp.md), [How to: Upload Files with FTP](how-to-upload-files-with-ftp.md), and [How to: List Directory Contents with FTP](how-to-list-directory-contents-with-ftp.md).</span></span>

## <a name="ftp-and-proxies"></a><span data-ttu-id="5a98c-109">FTP e proxy</span><span class="sxs-lookup"><span data-stu-id="5a98c-109">FTP and proxies</span></span>

<span data-ttu-id="5a98c-110">Se un proxy (specificato dalla proprietà <xref:System.Net.FtpWebRequest.Proxy%2A>) è un proxy HTTP, sono supportati solo i comandi <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory> e <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails>.</span><span class="sxs-lookup"><span data-stu-id="5a98c-110">If a proxy (specified by the <xref:System.Net.FtpWebRequest.Proxy%2A> property) is an HTTP proxy, then only the <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory>, and <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails> commands are supported.</span></span>

## <a name="see-also"></a><span data-ttu-id="5a98c-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a98c-111">See also</span></span>

- [<span data-ttu-id="5a98c-112">Accesso a Internet tramite un proxy</span><span class="sxs-lookup"><span data-stu-id="5a98c-112">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
- [<span data-ttu-id="5a98c-113">Esempi di programmazione di rete</span><span class="sxs-lookup"><span data-stu-id="5a98c-113">Network Programming Samples</span></span>](network-programming-samples.md)
- [<span data-ttu-id="5a98c-114">Uso di protocolli applicativi</span><span class="sxs-lookup"><span data-stu-id="5a98c-114">Using Application Protocols</span></span>](using-application-protocols.md)
