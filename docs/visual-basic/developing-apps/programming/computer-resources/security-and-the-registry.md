---
title: Sicurezza e Registro di sistema
ms.date: 07/20/2015
helpviewer_keywords:
- security [Visual Basic], registry
- registry [Visual Basic], security issues
ms.assetid: 9980aff7-2f69-492b-8f66-29a9a76d3df5
ms.openlocfilehash: 2eba9d177769b22de3f931bc7af4905a80e316b5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359968"
---
# <a name="security-and-the-registry-visual-basic"></a>Sicurezza e Registro di sistema (Visual Basic)

In questo argomento vengono illustrate le implicazioni in termini di sicurezza della memorizzazione dei dati nel Registro di sistema.  
  
## <a name="permissions"></a>Autorizzazioni  

 Archiviare come testo nel Registro di sistema informazioni riservate, quali le password, può presentare dei rischi, anche se la chiave del Registro di sistema è protetta da elenchi di controllo di accesso (ACL, Access Control List).  
  
 L'uso del Registro di sistema può compromettere la sicurezza poiché consente l'accesso inappropriato alle risorse di sistema o alle informazioni protette. Per usare tali proprietà, è necessario avere autorizzazioni di lettura e scrittura derivanti dall'enumerazione <xref:System.Security.Permissions.RegistryPermissionAccess> che controlla l'accesso alle variabili del Registro di sistema. Qualsiasi codice eseguito con attendibilità completa, che in base ai criteri di sicurezza predefiniti corrisponde al codice installato nel disco rigido locale dell'utente, ha le autorizzazioni necessarie per accedere al Registro di sistema. Per ulteriori informazioni, vedere la classe <xref:System.Security.Permissions.RegistryPermission>.  
  
 Le variabili del Registro di sistema non devono essere memorizzate in posizioni di memoria accessibili da codice senza <xref:System.Security.Permissions.RegistryPermission>. Analogamente, concedere i privilegi minimi necessari a eseguire il lavoro.  
  
 I valori di accesso alle autorizzazioni per il Registro di sistema sono definiti dall'enumerazione <xref:System.Security.Permissions.RegistryPermissionAccess>. Nella tabella riportata di seguito sono illustrati i dettagli dei membri.  
  
|valore|Accesso alle variabili del Registro di sistema|  
|-----------|----------------------------------|  
|`AllAccess`|Creazione, lettura e scrittura|  
|`Create`|Create|  
|`NoAccess`|Nessun accesso|  
|`Read`|Lettura|  
|`Write`|Scrittura|  
  
## <a name="checking-values-in-registry-keys"></a>Verifica dei valori nelle chiavi del Registro di sistema  

 Quando si crea un valore del Registro di sistema, è necessario decidere come procedere nel caso in cui tale valore esista già. È possibile che un altro processo, forse dannoso, abbia già creato il valore e possa accedervi. I dati inseriti nel valore del Registro di sistema sono disponibili per altri processi. Per evitare che ciò accada, usare il metodo `GetValue`. Restituisce `Nothing` se la chiave non esiste.  
  
> [!IMPORTANT]
> Durante la lettura del Registro di sistema da un'applicazione Web, l'identità dell'utente corrente dipende dall'autenticazione e dalla rappresentazione implementate nell'applicazione Web.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>
- [Lettura e scrittura nel Registro di sistema](reading-from-and-writing-to-the-registry.md)
