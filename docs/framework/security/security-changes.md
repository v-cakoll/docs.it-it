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
ms.openlocfilehash: af2869e5ca3b41778c094b7a78a9493e74868811
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204499"
---
# <a name="security-changes-in-the-net-framework"></a>Modifiche della sicurezza in .NET Framework

The most important change to security in the .NET Framework 4.5 is in strong naming. Per una descrizione delle modifiche, vedere [Enhanced Strong Naming](../../standard/assembly/enhanced-strong-naming.md) .  
  
.NET Framework offre un modello di sicurezza a due livelli per le applicazioni gestite. Windows 8.x Store apps run in a Windows security container that limits access to resources. All'interno del contenitore, le applicazioni gestite sono completamente attendibili. Da una prospettiva di sicurezza per l'accesso di codice (CAS), non c'è niente che uno sviluppatore possa fare per elevare il livello di privilegi. Per informazioni sui privilegi concessi da Windows, vedere [Dichiarazioni di funzionalità delle app (app di Windows Store)](https://go.microsoft.com/fwlink/?LinkId=230436) in Windows Dev Center. For information about creating a Windows 8.x Store app, see [Create your first Windows Store app using C# or Visual Basic](https://go.microsoft.com/fwlink/?LinkId=230461).
