---
title: Campo s_isDebuggerCheckDisabledForTestPurposes
ms.date: 03/30/2017
ms.technology:
- dotnet-wpf
api_name:
- System.Windows.Diagnostics.VisualDiagnostics.s_isDebuggerCheckDisabledForTestPurposes
api_location:
- PresentationCore.dll
api_type:
- Assembly
ms.assetid: 9033a513-c255-4f31-b6d7-09b8d8c50e2d
ms.openlocfilehash: f490ccb4675a434e3f3336723e321f256b10093d
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149176"
---
# <a name="sisdebuggercheckdisabledfortestpurposes-field"></a><span data-ttu-id="8794b-102">Campo s_isDebuggerCheckDisabledForTestPurposes</span><span class="sxs-lookup"><span data-stu-id="8794b-102">s_isDebuggerCheckDisabledForTestPurposes Field</span></span>

<span data-ttu-id="8794b-103">Questo campo privato all'interno di `System.Windows.Diagnostics.VisualDiagnostics` classe viene utilizzata da Visual Studio per determinare se verrà eseguito un controllo interno per un debugger attivo.</span><span class="sxs-lookup"><span data-stu-id="8794b-103">This private field in the `System.Windows.Diagnostics.VisualDiagnostics` class is used by Visual Studio to determine whether an internal check for an active debugger will be performed.</span></span>

## <a name="syntax"></a><span data-ttu-id="8794b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8794b-104">Syntax</span></span>
  
```csharp  
private static bool s_isDebuggerCheckDisabledForTestPurposes
```
  
> [!WARNING]
>  <span data-ttu-id="8794b-105">API nel `System.Windows.Diagnostics.VisualDiagnostics` classe sono disponibili solo quando un'applicazione è in esecuzione in un debugger.</span><span class="sxs-lookup"><span data-stu-id="8794b-105">API's in the `System.Windows.Diagnostics.VisualDiagnostics` class are only available when an application is running under a debugger.</span></span> <span data-ttu-id="8794b-106">Impostare `s_isDebuggerCheckDisabledForTestPurposes` a `true` per accedere alle API di fuori di un debugger.</span><span class="sxs-lookup"><span data-stu-id="8794b-106">Set `s_isDebuggerCheckDisabledForTestPurposes` to `true` to access the APIs outside of a debugger.</span></span>  
>   
>  <span data-ttu-id="8794b-107">Microsoft non supporta l'uso di questo campo in un'applicazione di produzione in alcuna circostanza.</span><span class="sxs-lookup"><span data-stu-id="8794b-107">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>  

## <a name="requirements"></a><span data-ttu-id="8794b-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8794b-108">Requirements</span></span>

<span data-ttu-id="8794b-109">**Spazio dei nomi:** <xref:System.Windows.Diagnostics></span><span class="sxs-lookup"><span data-stu-id="8794b-109">**Namespace:** <xref:System.Windows.Diagnostics></span></span>

<span data-ttu-id="8794b-110">**Assembly:** PresentationCore (in PresentationCore. dll)</span><span class="sxs-lookup"><span data-stu-id="8794b-110">**Assembly:** PresentationCore (in PresentationCore.dll)</span></span>

<span data-ttu-id="8794b-111">**Versioni di .NET framework:** Disponibile dalla 4.6.</span><span class="sxs-lookup"><span data-stu-id="8794b-111">**.NET Framework versions:** Available since 4.6.</span></span>