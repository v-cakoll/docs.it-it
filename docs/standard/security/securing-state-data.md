---
title: Protezione dei dati di stato
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- security [.NET Framework], state data
- code security, state data
- secure coding, state data
- state data security
ms.assetid: 12671309-2877-43fe-a3df-6863507e712d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fe941fff7091fb579e41a3c417dbb2129bcf3e8c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="securing-state-data"></a>Protezione dei dati di stato
Nelle applicazioni che consentono la gestione di dati sensibili o decisioni di qualsiasi tipo in materia di sicurezza è necessario mantenere il controllo dei dati e non consentire l'accesso diretto da parte di altro codice potenzialmente dannoso. Il modo migliore per proteggere i dati in memoria è dichiararli come variabili private o interne, ovvero con ambito limitato allo stesso assembly. Anche questi dati sono tuttavia soggetti a un tipo di accesso che è necessario determinare.  
  
-   Tramite meccanismi di reflection, è possibile ottenere e impostare membri privati in codice altamente attendibile che può fare riferimento all'oggetto.  
  
-   Tramite serializzazione, è possibile ottenere e impostare membri privati in codice altamente attendibile se è possibile accedere ai dati corrispondenti nella forma serializzata dell'oggetto.  
  
-   Nella fase di debug, questi dati possono essere letti.  
  
 Accertarsi che nessun metodo o proprietà esponga tali valori in modo non intenzionale.  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida per la generazione di codice sicuro](../../../docs/standard/security/secure-coding-guidelines.md)
