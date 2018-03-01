---
title: s_isDebuggerCheckDisabledForTestPurposes campo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
api_name:
- System.Windows.Diagnostics.VisualDiagnostics.s_isDebuggerCheckDisabledForTestPurposes
api_location:
- PresentationCore.dll
api_type:
- Assembly
ms.assetid: 9033a513-c255-4f31-b6d7-09b8d8c50e2d
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
robots: noindex,nofollow
ms.workload:
- dotnet
ms.openlocfilehash: 67da38d958d153ebe526f298785b39afb7be6513
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="sisdebuggercheckdisabledfortestpurposes-field"></a>s_isDebuggerCheckDisabledForTestPurposes campo

Questo campo privato all'interno di `System.Windows.Diagnostics.VisualDiagnostics` classe viene utilizzata da Visual Studio per determinare se verrà eseguito un controllo interno per un debugger attivo.

## <a name="syntax"></a>Sintassi
  
```csharp  
private static bool s_isDebuggerCheckDisabledForTestPurposes
```
  
> [!WARNING]
>  API nel `System.Windows.Diagnostics.VisualDiagnostics` classe sono disponibili solo quando un'applicazione è in esecuzione in un debugger. Impostare `s_isDebuggerCheckDisabledForTestPurposes` a `true` per accedere alle API di fuori di un debugger.  
>   
>  Microsoft non supporta l'utilizzo di questo campo in un'applicazione di produzione in qualsiasi circostanza.  

## <a name="requirements"></a>Requisiti

**Namespace:**<xref:System.Windows.Diagnostics>

**Assembly:** PresentationCore (in PresentationCore. dll)

**Versioni di .NET framework:** disponibile dalla 4.6.
