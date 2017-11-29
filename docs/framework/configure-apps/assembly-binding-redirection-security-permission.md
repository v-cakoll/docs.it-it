---
title: Autorizzazione di sicurezza per il reindirizzamento delle versioni di assembly
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: ddaf9965a3b3b5d6171a643b198db93309afad48
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="assembly-binding-redirection-security-permission"></a>Autorizzazione di sicurezza per il reindirizzamento delle versioni di assembly
Il reindirizzamento esplicito dell'associazione di assembly in un file di configurazione di un'applicazione richiede un'autorizzazione di sicurezza, che vale per il reindirizzamento degli assembly .NET Framework e di quelli di altri produttori. L'autorizzazione viene concessa impostando il <xref:System.Security.Permissions.SecurityPermissionFlag> flag di <xref:System.Security.Permissions.SecurityPermission>. Gli assembly gestiti non dispongono di autorizzazioni per impostazione predefinita.  
  
 Per le applicazioni in esecuzione nell'area attendibile (computer locale) e nell'area Intranet, viene concessa l'autorizzazione di sicurezza. Le applicazioni in esecuzione nell'area Internet non è assolutamente consentite di eseguire il reindirizzamento dell'associazione di assembly.  
  
 L'autorizzazione non è necessaria se il reindirizzamento di assembly viene eseguito in un file dei criteri editore controllato dall'editore del componente o nel file di configurazione del computer che viene controllato dall'amministratore. Tuttavia, l'autorizzazione è necessaria per un'applicazione ignorare in modo esplicito criteri editore utilizzando il [ \<publisherPolicy applicare = "no" / >](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) elemento nel file di configurazione dell'applicazione.  
  
 La tabella seguente mostra il valore predefinito di impostazioni di sicurezza per il **BindingRedirects** flag.  
  
|Zona|Impostazione del flag BindingRedirects|  
|----------|-----------------------------------|  
|Area siti attendibili (computer locale)|**ON**|  
|L'area Intranet|**ON**|  
|Area Internet|**DISATTIVATO**|  
|Zone non attendibili|**DISATTIVATO**|  
  
 Un amministratore può modificare queste impostazioni di sicurezza per il supporto o limitare per scenari specifici su un determinato computer. Non sono disponibili strumenti per la modifica di **BindingRedirects** impostazione del flag dall'impostazione predefinita; un amministratore deve modificare manualmente il file Security. config sul computer dell'utente.  
  
## <a name="see-also"></a>Vedere anche  
 [File dei criteri editore e l'esecuzione Side-by-Side](http://msdn.microsoft.com/en-us/97a042be-4d72-40c3-91c0-76fd36bdf133)  
 [Procedura: abilitare e disabilitare il reindirizzamento di associazione automatico](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)  
 [Esecuzione side-by-Side](../../../docs/framework/deployment/side-by-side-execution.md)
