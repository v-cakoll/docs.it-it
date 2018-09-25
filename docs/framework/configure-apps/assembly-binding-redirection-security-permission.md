---
title: Autorizzazione di sicurezza per il reindirizzamento delle versioni di assembly
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
author: mcleblanc
ms.author: markl
ms.openlocfilehash: e6690a4f11bb1a88e2d77c67ccb29056c8e03f96
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47088661"
---
# <a name="assembly-binding-redirection-security-permission"></a>Autorizzazione di sicurezza per il reindirizzamento delle versioni di assembly
Il reindirizzamento esplicito dell'associazione di assembly in un file di configurazione di un'applicazione richiede un'autorizzazione di sicurezza, che vale per il reindirizzamento degli assembly .NET Framework e di quelli di altri produttori. L'autorizzazione viene concessa impostando il <xref:System.Security.Permissions.SecurityPermissionFlag> flag nella <xref:System.Security.Permissions.SecurityPermission>. Gli assembly gestiti non dispongono di autorizzazioni per impostazione predefinita.  
  
 Viene concessa l'autorizzazione di sicurezza alle applicazioni in esecuzione nell'area attendibile (computer locale) e nell'area Intranet. Le applicazioni in esecuzione nell'area Internet sono assolutamente consentite di eseguire il reindirizzamento di associazione di assembly.  
  
 L'autorizzazione non è obbligatorio se viene eseguito il reindirizzamento di assembly in un file di criteri di autore che è controllato dall'editore del componente, o nel file di configurazione del computer che viene controllato dall'amministratore. Tuttavia, l'autorizzazione è necessaria per un'applicazione ignorare in modo esplicito server di pubblicazione dei criteri tramite il [ \<publisherPolicy applicare = "no" / >](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) elemento nel file di configurazione dell'applicazione.  
  
 La tabella seguente mostra il valore predefinito delle impostazioni di sicurezza per il **BindingRedirects** flag.  
  
|Zona|Impostazione del flag BindingRedirects|  
|----------|-----------------------------------|  
|Area attendibile (computer locale)|**VIA**|  
|Area Intranet|**VIA**|  
|Area Internet|**OFF**|  
|Zone non attendibili|**OFF**|  
  
 Un amministratore può modificare queste impostazioni di sicurezza per il supporto o limitare gli scenari specifici in un determinato computer. Non sono disponibili strumenti per la modifica di **BindingRedirects** flag impostazione dal valore predefinito; un amministratore deve modificare manualmente il file Security. config nel computer dell'utente.  
  
## <a name="see-also"></a>Vedere anche  
 [File dei criteri editore ed esecuzione Side-by-Side](https://msdn.microsoft.com/library/97a042be-4d72-40c3-91c0-76fd36bdf133)  
 [Procedura: abilitare e disabilitare il reindirizzamento di associazione automatico](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)  
 [Esecuzione side-by-side](../../../docs/framework/deployment/side-by-side-execution.md)
