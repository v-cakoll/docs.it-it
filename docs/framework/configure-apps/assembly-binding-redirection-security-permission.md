---
title: Autorizzazione di sicurezza per il reindirizzamento delle versioni di assembly
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
ms.openlocfilehash: b59689e78f901637674c0a1df28ed74411e8e7c7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921383"
---
# <a name="assembly-binding-redirection-security-permission"></a>Autorizzazione di sicurezza per il reindirizzamento delle versioni di assembly
Il reindirizzamento esplicito dell'associazione di assembly in un file di configurazione di un'applicazione richiede un'autorizzazione di sicurezza, che vale per il reindirizzamento degli assembly .NET Framework e di quelli di altri produttori. L'autorizzazione viene concessa impostando <xref:System.Security.Permissions.SecurityPermissionFlag> il flag <xref:System.Security.Permissions.SecurityPermission>su. Per impostazione predefinita, gli assembly gestiti non dispongono di autorizzazioni.  
  
 L'autorizzazione di sicurezza viene concessa alle applicazioni in esecuzione nell'area attendibile (computer locale) e nell'area Intranet. Le applicazioni in esecuzione nell'area Internet sono strettamente proibite dall'esecuzione del reindirizzamento dell'associazione di assembly.  
  
 L'autorizzazione non è necessaria se il reindirizzamento degli assembly viene eseguito in un file dei criteri editore controllato dall'autore del componente o nel file di configurazione del computer controllato dall'amministratore. Tuttavia, l'autorizzazione è necessaria affinché un'applicazione ignori esplicitamente i criteri di pubblicazione utilizzando l' [ \<elemento publisherPolicy apply Apply = "No"/>](./file-schema/runtime/publisherpolicy-element.md) nel file di configurazione dell'applicazione.  
  
 Nella tabella seguente vengono illustrate le impostazioni di sicurezza predefinite per il flag **BindingRedirects** .  
  
|Zona|Impostazione del flag BindingRedirects|  
|----------|-----------------------------------|  
|Area attendibile (computer locale)|**ON**|  
|Area Intranet|**ON**|  
|Area Internet|**OFF**|  
|Zone non attendibili|**OFF**|  
  
 Un amministratore può modificare queste impostazioni di sicurezza per supportare o limitare scenari specifici in un determinato computer. Non sono disponibili strumenti per modificare l'impostazione del flag **BindingRedirects** dal valore predefinito. un amministratore deve modificare manualmente il file Security. config nel computer di un utente.  
  
## <a name="see-also"></a>Vedere anche

- [File di criteri editore ed esecuzione side-by-side](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/06d2bae3(v=vs.100))
- [Procedura: Abilitare e disabilitare il reindirizzamento di associazione automatico](how-to-enable-and-disable-automatic-binding-redirection.md)
- [Esecuzione side-by-side](../deployment/side-by-side-execution.md)
