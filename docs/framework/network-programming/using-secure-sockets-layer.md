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
- VB
- CSharp
- C++
- jsharp
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
caps.latest.revision: 14
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: cb625971f0c0b52bcdcfc9b41d4c0f88814aef08
ms.contentlocale: it-it
ms.lasthandoff: 08/21/2017

---
# <a name="using-secure-sockets-layer"></a>Uso di Secure Sockets Layer
Le classi <xref:System.Net> usano Secure Sockets Layer (SSL) per crittografare la connessione per diversi protocolli di rete.  
  
 Per le connessioni HTTP, le classi <xref:System.Net.WebRequest> e <xref:System.Net.WebResponse> usano SSL per comunicare con host Web che supportano SSL. La decisione di usare SSL avviene tramite la classe <xref:System.Net.WebRequest>, in base all'URI assegnato. Se l'URI inizia con "https:", viene usato SSL. Se l'URI inizia con "http:", viene usata una connessione non crittografata.  
  
 Per usare SSL con FTP (File Transfer Protocol), impostare la proprietà <xref:System.Net.FtpWebRequest.EnableSsl> su true prima di chiamare <xref:System.Net.FtpWebRequest.GetResponse>. Analogamente, per usare SSL con SMTP (Simple Mail Transport Protocol), impostare la proprietà <xref:System.Net.Mail.SmtpClient.EnableSsl> su true prima di inviare messaggi di posta elettronica.  
  
 La classe <xref:System.Net.Security.SslStream> fornisce un'astrazione basata su flussi per SSL e offre diversi modi per configurare l'handshake SSL.  
  
## <a name="example"></a>Esempio  
  
### <a name="code"></a>Codice  
  
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
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Riferimenti allo spazio dei nomi **System.Net**.  
  
## <a name="see-also"></a>Vedere anche  
 [Sicurezza nella programmazione di rete](../../../docs/framework/network-programming/security-in-network-programming.md)   
 [Programmazione di rete in .NET Framework](../../../docs/framework/network-programming/index.md)   
 [Selezione e convalida dei certificati](../../../docs/framework/network-programming/certificate-selection-and-validation.md)

