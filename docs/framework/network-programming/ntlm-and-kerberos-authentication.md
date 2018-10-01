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
# <a name="ntlm-and-kerberos-authentication"></a><span data-ttu-id="df4d1-102">Autenticazione NTLM e Kerberos</span><span class="sxs-lookup"><span data-stu-id="df4d1-102">NTLM and Kerberos Authentication</span></span>
<span data-ttu-id="df4d1-103">L'autenticazione NTLM predefinita e l'autenticazione Kerberos usano le credenziali utente di Microsoft Windows NT associate all'applicazione chiamante per tentare l'autenticazione nel server.</span><span class="sxs-lookup"><span data-stu-id="df4d1-103">Default NTLM authentication and Kerberos authentication use the Microsoft Windows NT user credentials associated with the calling application to attempt authentication with the server.</span></span> <span data-ttu-id="df4d1-104">Quando si usa l'autenticazione NTLM non predefinita, l'applicazione imposta il tipo di autenticazione su NTLM e usa un oggetto <xref:System.Net.NetworkCredential> per passare nome utente, password e dominio all'host, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="df4d1-104">When using non-default NTLM authentication, the application sets the authentication type to NTLM and uses a <xref:System.Net.NetworkCredential> object to pass the user name, password, and domain to the host, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="df4d1-105">Le applicazioni che devono connettersi a servizi Internet con le credenziali dell'utente dell'applicazione possono farlo con le credenziali predefinite dell'utente, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="df4d1-105">Applications that need to connect to Internet services using the credentials of the application user can do so with the user's default credentials, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="df4d1-106">Il modulo di autenticazione negotiate determina se il server remoto usa l'autenticazione NTLM o Kerberos e invia la risposta appropriata.</span><span class="sxs-lookup"><span data-stu-id="df4d1-106">The negotiate authentication module determines whether the remote server is using NTLM or Kerberos authentication, and sends the appropriate response.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="df4d1-107">L'autenticazione NTLM non funziona tramite un server proxy.</span><span class="sxs-lookup"><span data-stu-id="df4d1-107">NTLM authentication does not work through a proxy server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df4d1-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df4d1-108">See Also</span></span>  
 [<span data-ttu-id="df4d1-109">Autenticazione di base e del digest</span><span class="sxs-lookup"><span data-stu-id="df4d1-109">Basic and Digest Authentication</span></span>](../../../docs/framework/network-programming/basic-and-digest-authentication.md)  
 [<span data-ttu-id="df4d1-110">Autenticazione Internet</span><span class="sxs-lookup"><span data-stu-id="df4d1-110">Internet Authentication</span></span>](../../../docs/framework/network-programming/internet-authentication.md)
