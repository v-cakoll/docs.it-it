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
ms.openlocfilehash: f4cf91924e762495df6787a187e4295b69f2cd96
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71045381"
---
# <a name="security-changes-in-the-net-framework"></a>Modifiche della sicurezza in .NET Framework

Il passaggio più importante alla sicurezza nella .NET Framework 4,5 è la denominazione sicura. Per una descrizione delle modifiche, vedere [Enhanced Strong Naming](../../standard/assembly/enhanced-strong-naming.md) .  
  
.NET Framework offre un modello di sicurezza a due livelli per le applicazioni gestite. Le applicazioni[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] vengono eseguite in un contenitore di sicurezza di Windows tramite cui viene limitato l'accesso alle risorse. All'interno del contenitore, le applicazioni gestite sono completamente attendibili. Da una prospettiva di sicurezza per l'accesso di codice (CAS), non c'è niente che uno sviluppatore possa fare per elevare il livello di privilegi. Per informazioni sui privilegi concessi da Windows, vedere [Dichiarazioni di funzionalità delle app (app di Windows Store)](https://go.microsoft.com/fwlink/?LinkId=230436) in Windows Dev Center. Per informazioni sulla creazione di un'app [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] , vedere [Creare la prima app di Windows Store in C# o Visual Basic](https://go.microsoft.com/fwlink/?LinkId=230461).
