---
title: Autenticazione NTLM e Kerberos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
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
ms.openlocfilehash: 372101763bdd84b454e6e2db3ec6cf0ebdf3f991
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180697"
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
> L'autenticazione NTLM non funziona tramite un server proxy.  
  
## <a name="see-also"></a>Vedere anche

- [Autenticazione di base e digestBasic and Digest Authentication](basic-and-digest-authentication.md)
- [Autenticazione Internet](internet-authentication.md)
