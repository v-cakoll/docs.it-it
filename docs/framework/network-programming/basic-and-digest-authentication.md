---
title: Autenticazione di base e del digest
description: Informazioni su come usare l'autenticazione di base e del digest, in cui un'applicazione fornisce un nome utente e una password nell'oggetto WebRequest usato per richiedere i dati.
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
ms.openlocfilehash: 7772430b508b52a63d716550b69018385418c132
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502698"
---
# <a name="basic-and-digest-authentication"></a>Autenticazione di base e del digest
L'implementazione <xref:System.Net> dell'autenticazione di base e digest è conforme alla specifica RFC2617 - HTTP Authentication: Basic and Digest Authentication, disponibile nel sito Web del [World Wide Web Consortium](https://www.w3.org).  
  
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
> I dati inviati con l'autenticazione di base o digest non sono crittografati, pertanto possono essere visti da un antagonista. Le credenziali di autenticazione di base (nome utente e password) vengono inoltre inviate in testo non crittografato e possono essere intercettate.  
  
## <a name="see-also"></a>Vedere anche

- [Autenticazione NTLM e Kerberos](ntlm-and-kerberos-authentication.md)
- [Autenticazione Internet](internet-authentication.md)
