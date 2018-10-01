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
author: mcleblanc
ms.author: markl
ms.openlocfilehash: e7638b9558363b77b03208d86d98330b922b414c
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47195478"
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
