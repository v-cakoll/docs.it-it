---
title: Autenticazione di base e del digest
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- authentication [.NET Framework], classes
- Basic authentication
- authentication [.NET Framework], basic
- client authentication, basic
- user authentication, basic
- authentication [.NET Framework], digest
- receiving data, authentication
- client authentication, digest
- Internet, authentication
- digest authentication
- sending data, authentication
- network resources, authentication
- user authentication, digest
ms.assetid: 8cce2742-8d52-4643-9dd2-64ddf38aa878
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 66b20c299252ff1f218a8131758e2cf03640aac6
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47199538"
---
# <a name="basic-and-digest-authentication"></a>Autenticazione di base e del digest
L'implementazione <xref:System.Net> dell'autenticazione di base e digest è conforme alla specifica RFC2617 - HTTP Authentication: Basic and Digest Authentication, disponibile in lingua inglese sul sito Web del World Wide Web Consortium all'indirizzo www.w3.org.  
  
 Per poter usare l'autenticazione di base e digest in un'applicazione, è necessario che vengano specificati un nome utente e una password nella proprietà <xref:System.Net.WebRequest.Credentials%2A> dell'oggetto <xref:System.Net.WebRequest> usato per richiedere dati da Internet, come illustrato nell'esempio seguente.  
  
```vb  
Dim MyURI As String = "http://www.contoso.com/"  
Dim WReq As WebRequest = WebRequest.Create(MyURI)  
WReq.Credentials = New NetworkCredential(UserName, SecurelyStoredPassword)  
```  
  
```csharp  
String MyURI = "http://www.contoso.com/";  
WebRequest WReq = WebRequest.Create(MyURI);  
WReq.Credentials = new NetworkCredential(UserName, SecurelyStoredPassword);  
```  
  
> [!CAUTION]
>  I dati inviati con l'autenticazione di base o digest non sono crittografati, pertanto possono essere visti da un antagonista. Le credenziali di autenticazione di base (nome utente e password) vengono inoltre inviate in testo non crittografato e possono essere intercettate.  
  
## <a name="see-also"></a>Vedere anche  
 [Autenticazione NTLM e Kerberos](../../../docs/framework/network-programming/ntlm-and-kerberos-authentication.md)  
 [Autenticazione Internet](../../../docs/framework/network-programming/internet-authentication.md)
