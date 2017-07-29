---
title: Sicurezza e Registro di sistema (Visual Basic)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- security [Visual Basic], registry
- registry, security issues
ms.assetid: 9980aff7-2f69-492b-8f66-29a9a76d3df5
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2ca25e9ce82baf9d9f59ecd887aaf2cbb301f4e3
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="security-and-the-registry-visual-basic"></a>Sicurezza e Registro di sistema (Visual Basic)
In questo argomento vengono illustrate le implicazioni in termini di sicurezza della memorizzazione dei dati nel Registro di sistema.  
  
## <a name="permissions"></a>Autorizzazioni  
 Archiviare come testo nel Registro di sistema informazioni riservate, quali le password, può presentare dei rischi, anche se la chiave del Registro di sistema è protetta da elenchi di controllo di accesso (ACL, Access Control List).  
  
 L'uso del Registro di sistema può compromettere la sicurezza poiché consente l'accesso inappropriato alle risorse di sistema o alle informazioni protette. Per usare tali proprietà, è necessario avere autorizzazioni di lettura e scrittura derivanti dall'enumerazione <xref:System.Security.Permissions.RegistryPermissionAccess> che controlla l'accesso alle variabili del Registro di sistema. Qualsiasi codice eseguito con attendibilità completa, che in base ai criteri di sicurezza predefiniti corrisponde al codice installato nel disco rigido locale dell'utente, ha le autorizzazioni necessarie per accedere al Registro di sistema. Per altre informazioni, vedere la classe <xref:System.Security.Permissions.RegistryPermission>.  
  
 Le variabili del Registro di sistema non devono essere memorizzate in posizioni di memoria accessibili da codice senza <xref:System.Security.Permissions.RegistryPermission>. Analogamente, concedere i privilegi minimi necessari a eseguire il lavoro.  
  
 I valori di accesso alle autorizzazioni per il Registro di sistema sono definiti dall'enumerazione <xref:System.Security.Permissions.RegistryPermissionAccess>. Nella tabella riportata di seguito sono illustrati i dettagli dei membri.  
  
|Valore|Accesso alle variabili del Registro di sistema|  
|-----------|----------------------------------|  
|`AllAccess`|Creazione, lettura e scrittura|  
|`Create`|Crea|  
|`NoAccess`|Nessun accesso|  
|`Read`|Lettura|  
|`Write`|Write|  
  
## <a name="checking-values-in-registry-keys"></a>Verifica dei valori nelle chiavi del Registro di sistema  
 Quando si crea un valore del Registro di sistema, è necessario decidere come procedere nel caso in cui tale valore esista già. È possibile che un altro processo, forse dannoso, abbia già creato il valore e possa accedervi. I dati inseriti nel valore del Registro di sistema sono disponibili per altri processi. Per evitare che ciò accada, usare il metodo `GetValue`. Restituisce `Nothing` se la chiave non esiste.  
  
> [!IMPORTANT]
>  Durante la lettura del Registro di sistema da un'applicazione Web, l'identità dell'utente corrente dipende dall'autenticazione e dalla rappresentazione implementate nell'applicazione Web.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>   
 [Lettura e scrittura nel Registro di sistema](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)

