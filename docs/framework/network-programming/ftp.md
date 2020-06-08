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
# <a name="ftp"></a>FTP

.NET Framework offre supporto completo per il protocollo FTP con le classi <xref:System.Net.FtpWebRequest> e <xref:System.Net.FtpWebResponse>. Queste classi sono derivate da <xref:System.Net.WebRequest> e <xref:System.Net.WebResponse>. Nella maggior parte dei casi, le classi <xref:System.Net.WebRequest> e <xref:System.Net.WebResponse> rendono disponibile tutto ciò che serve per eseguire la richiesta. Se tuttavia è necessario accedere alle funzionalità specifiche di FTP esposte come proprietà, è possibile eseguire il cast di tipo di queste classi a <xref:System.Net.FtpWebRequest> o <xref:System.Net.FtpWebResponse>.

## <a name="examples"></a>Esempi

Per altre informazioni, vedere gli argomenti seguenti: [Procedura: Scaricare file con FTP](how-to-download-files-with-ftp.md), [Procedura: Caricare file con FTP](how-to-upload-files-with-ftp.md), e [Procedura: Elencare il contenuto della directory con FTP](how-to-list-directory-contents-with-ftp.md).

## <a name="ftp-and-proxies"></a>FTP e proxy

Se un proxy (specificato dalla proprietà <xref:System.Net.FtpWebRequest.Proxy%2A>) è un proxy HTTP, sono supportati solo i comandi <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory> e <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails>.

## <a name="see-also"></a>Vedere anche

- [Accesso a Internet tramite un proxy](accessing-the-internet-through-a-proxy.md)
- [Esempi di programmazione di rete](network-programming-samples.md)
- [Uso di protocolli applicativi](using-application-protocols.md)
