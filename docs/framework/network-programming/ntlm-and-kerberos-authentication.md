---
title: Autenticazione NTLM e Kerberos
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
- authentication [.NET Framework], NTLM
- authentication [.NET Framework], Kerberos
- user authentication, Kerberos
- user authentication, NTLM
- Kerberos authentication
- receiving data, authentication
- NTLM authentication
- Internet, authentication
- client authentication, Kerberos
- sending data, authentication
- network resources, authentication
- classes [.NET Framework], authentication
- client authentication, NTLM
ms.assetid: 9ef65560-f596-4469-bcce-f4d5407b55cd
caps.latest.revision: 9
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8cb52a70aa34e1011f12a77ea32ec5077f92c127
ms.contentlocale: it-it
ms.lasthandoff: 08/21/2017

---
# <a name="ntlm-and-kerberos-authentication"></a>Autenticazione NTLM e Kerberos
L'autenticazione NTLM predefinita e l'autenticazione Kerberos usano le credenziali utente di Microsoft Windows NT associate all'applicazione chiamante per tentare l'autenticazione nel server. Quando si usa l'autenticazione NTLM non predefinita, l'applicazione imposta il tipo di autenticazione su NTLM e usa un oggetto <xref:System.Net.NetworkCredential> per passare nome utente, password e dominio all'host, come illustrato nell'esempio seguente.  
  
```vb  
Dim MyURI As String = "http://www.contoso.com/"  
Dim WReq As WebRequest = WebRequest.Create(MyURI)  
WReq.Credentials = _  
    New NetworkCredential(UserName, SecurelyStoredPassword, Domain)  
```  
  
```csharp  
String MyURI = "http://www.contoso.com/";  
WebRequest WReq = WebRequest.Create (MyURI);  
WReq.Credentials =   
    new NetworkCredential(UserName, SecurelyStoredPassword, Domain);  
```  
  
 Le applicazioni che devono connettersi a servizi Internet con le credenziali dell'utente dell'applicazione possono farlo con le credenziali predefinite dell'utente, come illustrato nell'esempio seguente.  
  
```vb  
Dim MyURI As String = "http://www.contoso.com/"  
Dim WReq As WebRequest = WebRequest.Create(MyURI)  
WReq.Credentials = CredentialCache.DefaultCredentials  
```  
  
```csharp  
String MyURI = "http://www.contoso.com/";  
WebRequest WReq = WebRequest.Create (MyURI);  
WReq.Credentials = CredentialCache.DefaultCredentials;  
```  
  
 Il modulo di autenticazione negotiate determina se il server remoto usa l'autenticazione NTLM o Kerberos e invia la risposta appropriata.  
  
> [!NOTE]
>  L'autenticazione NTLM non funziona tramite un server proxy.  
  
## <a name="see-also"></a>Vedere anche  
 [Autenticazione di base e del digest](../../../docs/framework/network-programming/basic-and-digest-authentication.md)   
 [Autenticazione Internet](../../../docs/framework/network-programming/internet-authentication.md)

