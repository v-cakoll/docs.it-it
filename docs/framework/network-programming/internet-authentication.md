---
title: Autenticazione Internet
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [.NET Framework], classes
- IAuthenticationModule interface
- ICredentialLookup interface
- CredentialCache class, about CredentialCache class
- receiving data, authentication
- AuthenticationManager class, about AuthenticationManager class
- Internet, authentication
- sending data, authentication
- network resources, authentication
- user authentication, classes for authentication
- NetworkCredential class, about NetworkCredential class
- client authentication, classes for authentication
ms.assetid: d342e87c-f672-4660-a513-41a2f2b80c4a
ms.openlocfilehash: 3e0b5cd58270cec758db5d4dad6f3ad48962921a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047912"
---
# <a name="internet-authentication"></a>Autenticazione Internet
Le classi <xref:System.Net> supportano svariati meccanismi di autenticazione client, inclusi i metodi di autenticazione Internet standard come l'autenticazione di base, digest, di negoziazione, NTLM e Kerberos, nonché metodi personalizzati che è possibile creare.  
  
 Le credenziali di autenticazione sono archiviate nelle classi <xref:System.Net.NetworkCredential> e <xref:System.Net.CredentialCache>, che implementano l'interfaccia <xref:System.Net.ICredentials>. Quando su una di queste classi viene eseguita una query per richiedere le credenziali, la query restituisce un'istanza della classe **NetworkCredential**. Il processo di autenticazione viene gestito dalla classe <xref:System.Net.AuthenticationManager>, mentre l'effettivo processo di autenticazione viene eseguito da una classe del modulo di autenticazione che implementa l'interfaccia <xref:System.Net.IAuthenticationModule>. È necessario registrare un modulo di autenticazione personalizzato con **AuthenticationManager** prima di poterlo usare. I metodi di autenticazione di base, digest, di negoziazione, NTLM e Kerberos sono registrati per impostazione predefinita.  
  
 **NetworkCredential** archivia un set di credenziali associate a una singola risorsa Internet identificata da un URI e restituisce le credenziali in risposta a qualsiasi chiamata al metodo <xref:System.Net.NetworkCredential.GetCredential%2A>. La classe **NetworkCredential** è in genere usata da applicazioni che accedono a un numero limitato di risorse Internet o da applicazioni che usano lo stesso set di credenziali in tutti i casi.  
  
 La classe **CredentialCache** archivia una raccolta di credenziali per diverse risorse Web. Quando viene chiamato il metodo <xref:System.Net.CredentialCache.GetCredential%2A>, **CredentialCache** restituisce il set di credenziali corretto, determinato dall'URI della risorsa Web e dallo schema di autenticazione richiesto. Le applicazioni che usano un'ampia gamma di risorse Internet con schemi di autenticazione diversi traggono vantaggio dall'uso della classe **CredentialCache**, che archivia tutte le credenziali e le fornisce in base alle richieste.  
  
 Quando una risorsa Internet richiede l'autenticazione, il metodo <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType> invia <xref:System.Net.WebRequest> a **AuthenticationManager** insieme alla richiesta di credenziali. La richiesta viene quindi autenticata in base al processo seguente:  
  
1. **AuthenticationManager** chiama il metodo <xref:System.Net.IAuthenticationModule.Authenticate%2A> in ognuno dei moduli di autenticazione registrati, nell'ordine in cui sono stati registrati. **AuthenticationManager** usa il primo modulo che non restituisce **null** per eseguire il processo di autenticazione. I dettagli del processo variano a seconda del tipo di modulo di autenticazione coinvolto.  
  
2. Quando il processo di autenticazione è completo, il modulo di autenticazione restituisce un oggetto <xref:System.Net.Authorization> a **WebRequest** che contiene le informazioni necessarie per accedere alla risorsa Internet.  
  
 Alcuni schemi di autenticazione possono autenticare un utente senza prima eseguire la richiesta di una risorsa. Un'applicazione può risparmiare tempo tramite la preautenticazione dell'utente con la risorsa, eliminando in questo modo almeno un round trip al server. In alternativa, l'applicazione può eseguire l'autenticazione durante l'avvio del programma per rispondere più rapidamente all'utente in seguito. Gli schemi di autenticazione che possono usare la preautenticazione impostano la proprietà <xref:System.Net.IAuthenticationModule.PreAuthenticate%2A> su **true**.  
  
## <a name="see-also"></a>Vedere anche

- [Autenticazione di base e digestBasic and Digest Authentication](basic-and-digest-authentication.md)
- [Autenticazione NTLM e Kerberos](ntlm-and-kerberos-authentication.md)
- [Sicurezza nella programmazione di rete](security-in-network-programming.md)
