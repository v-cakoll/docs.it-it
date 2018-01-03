---
title: FTP
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: FTP
ms.assetid: 9b43f8b4-89d7-46a7-89fc-71aca916dd32
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 6c0e0172bc42b0b14eebdeaba85d454c5aec25c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ftp"></a>FTP
.NET Framework offre supporto completo per il protocollo FTP con le classi <xref:System.Net.FtpWebRequest> e <xref:System.Net.FtpWebResponse>. Queste classi sono derivate da <xref:System.Net.WebRequest> e <xref:System.Net.WebResponse>. Nella maggior parte dei casi, le classi <xref:System.Net.WebRequest> e <xref:System.Net.WebResponse> rendono disponibile tutto ciò che serve per eseguire la richiesta. Se tuttavia è necessario accedere alle funzionalità specifiche di FTP esposte come proprietà, è possibile eseguire il cast di tipo di queste classi a <xref:System.Net.FtpWebRequest> o <xref:System.Net.FtpWebResponse>.  
  
## <a name="examples"></a>Esempi  
 Per altre informazioni, vedere gli argomenti seguenti: [Procedura: Scaricare file con FTP](../../../docs/framework/network-programming/how-to-download-files-with-ftp.md), [Procedura: Caricare file con FTP](../../../docs/framework/network-programming/how-to-upload-files-with-ftp.md), e [Procedura: Elencare il contenuto della directory con FTP](../../../docs/framework/network-programming/how-to-list-directory-contents-with-ftp.md).  
  
## <a name="ftp-and-proxies"></a>FTP e proxy  
 Se un proxy (specificato dalla proprietà <xref:System.Net.FtpWebRequest.Proxy%2A>) è un proxy HTTP, sono supportati solo i comandi <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory> e <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails>.  
  
## <a name="see-also"></a>Vedere anche  
 [Accesso a Internet con un proxy](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [Esempi di programmazione di rete](../../../docs/framework/network-programming/network-programming-samples.md)  
 [FTP Client Technology Sample](http://go.microsoft.com/fwlink/?LinkID=179557) (Esempio di tecnologia client FTP)  
 [FTP Explorer Technology Sample](http://go.microsoft.com/fwlink/?LinkID=179569) (Esempio di tecnologia esplora risorse FTP)  
 [Uso di protocolli applicativi](../../../docs/framework/network-programming/using-application-protocols.md)
