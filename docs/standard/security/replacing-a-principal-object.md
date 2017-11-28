---
title: Sostituzione di oggetti Principal
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- principal objects, replacing
- security [.NET Framework], replacing principal objects
- security [.NET Framework], principals
ms.assetid: c323687e-b196-487b-beba-f38f9b3f961b
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 066176d39f04165d7882a3c295387847a46c8e6c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="replacing-a-principal-object"></a>Sostituzione di oggetti Principal
Le applicazioni che forniscono servizi di autenticazione devono poter sostituire l'oggetto **Principal** (<xref:System.Security.Principal.IPrincipal>) per un determinato thread. Inoltre, il sistema di sicurezza deve garantire la possibilità di sostituire gli oggetti **Principal** perché un oggetto **Principal** non corretto collegato in modo intenzionalmente dannoso compromette la sicurezza dell'applicazione attestando un identità o un ruolo non true. Pertanto, le applicazioni che richiedono la possibilità di sostituire **principale** oggetti devono essere concesse le <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType> oggetto per il controllo dell'entità. Tenere presente che questa autorizzazione non è necessaria per eseguire controlli di sicurezza basata sui ruoli o per creare oggetti **Principal** .  
  
 L'oggetto **Principal** corrente può essere sostituito eseguendo le attività seguenti:  
  
1.  Creare l'oggetto **Principal** di sostituzione e l'oggetto **Identity** associato.  
  
2.  Associare il nuovo oggetto **Principal** al contesto chiamata.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come creare un oggetto identità generico e usarlo per impostare l'identità di un thread.  
  
 [!code-csharp[SetCurrentPrincipal#1](../../../samples/snippets/csharp/VS_Snippets_CLR/SetCurrentPrincipal/CS/program.cs#1)]
 [!code-vb[SetCurrentPrincipal#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/SetCurrentPrincipal/VB/program.vb#1)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType>  
 [Oggetti Principal e Identity](../../../docs/standard/security/principal-and-identity-objects.md)
