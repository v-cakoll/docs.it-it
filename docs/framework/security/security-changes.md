---
title: Modifiche della sicurezza in .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- Allow Partially Trusted Callers attribute
- .NET Framework 4, security changes
- .NET Framework security
- security-transparent code
- security-critical code
- code access security, changes
ms.assetid: 5e87881c-9c13-4b52-8ad1-e34bb46e8aaa
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 84e80b99ee6d872714180e73354d20770c21e144
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="security-changes-in-the-net-framework"></a>Modifiche della sicurezza in .NET Framework
La modifica più importante apportata alla sicurezza in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] è costituita dall'assegnazione di nomi sicuri. Per una descrizione delle modifiche, vedere [Enhanced Strong Naming](../../../docs/framework/app-domains/enhanced-strong-naming.md) .  
  
 .NET Framework offre un modello di sicurezza a due livelli per le applicazioni gestite. Le applicazioni[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] vengono eseguite in un contenitore di sicurezza di Windows tramite cui viene limitato l'accesso alle risorse. All'interno del contenitore, le applicazioni gestite sono completamente attendibili. Da una prospettiva di sicurezza per l'accesso di codice (CAS), non c'è niente che uno sviluppatore possa fare per elevare il livello di privilegi. Per informazioni sui privilegi concessi da Windows, vedere [Dichiarazioni di funzionalità delle app (app di Windows Store)](http://go.microsoft.com/fwlink/?LinkId=230436) in Windows Dev Center. Per informazioni sulla creazione di un'app [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] , vedere [Creare la prima app di Windows Store in C# o Visual Basic](http://go.microsoft.com/fwlink/?LinkId=230461).
