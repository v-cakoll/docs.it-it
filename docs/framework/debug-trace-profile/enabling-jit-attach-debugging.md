---
title: Attivazione dell'esecuzione del debug ad associazione JIT
ms.date: 03/30/2017
helpviewer_keywords:
- JIT-attach debugging
- debugging [.NET Framework], JIT-attach debugging
ms.assetid: f91fc5f7-de5a-4f23-b6ac-f450e63c662e
author: mairaw
ms.author: mairaw
ms.openlocfilehash: be619f8e84b176872361fdd43faa9c704832c8e0
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975593"
---
# <a name="enabling-jit-attach-debugging"></a><span data-ttu-id="9b04d-102">Attivazione dell'esecuzione del debug ad associazione JIT</span><span class="sxs-lookup"><span data-stu-id="9b04d-102">Enabling JIT-Attach Debugging</span></span>
<span data-ttu-id="9b04d-103">Il termine debug ad associazione JIT indica l'associazione di un debugger a un processo in caso di errori. Può anche essere attivato da specifici metodi o funzioni.</span><span class="sxs-lookup"><span data-stu-id="9b04d-103">JIT-attach debugging is the phrase used to describe attaching a debugger to a process when you encounter errors, or it can be triggered by specific methods or functions.</span></span>  
  
 <span data-ttu-id="9b04d-104">Il debug ad associazione JIT viene usato con le condizioni di errore seguenti:</span><span class="sxs-lookup"><span data-stu-id="9b04d-104">JIT-attach debugging is used under the following fault conditions:</span></span>  
  
- <span data-ttu-id="9b04d-105">Eccezioni non gestite (sia nel codice gestito che in quello nativo).</span><span class="sxs-lookup"><span data-stu-id="9b04d-105">Unhandled exceptions (in both native and managed code).</span></span>  
  
- <span data-ttu-id="9b04d-106">Metodo <xref:System.Environment.FailFast%2A?displayProperty=nameWithType> o funzione [RaiseFailFastException](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raisefailfastexception) (famiglia Windows 7).</span><span class="sxs-lookup"><span data-stu-id="9b04d-106"><xref:System.Environment.FailFast%2A?displayProperty=nameWithType> method or [RaiseFailFastException](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raisefailfastexception) function (Windows 7 family).</span></span>  
  
- <span data-ttu-id="9b04d-107">Errori irreversibili di runtime.</span><span class="sxs-lookup"><span data-stu-id="9b04d-107">Runtime fatal errors.</span></span>  
  
 <span data-ttu-id="9b04d-108">Il debug ad associazione JIT viene attivato anche dalle chiamate ai metodi e alle funzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9b04d-108">JIT-attach debugging is also triggered by calls to the following methods and functions:</span></span>  
  
- <span data-ttu-id="9b04d-109">Metodo<xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="9b04d-109"><xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> method.</span></span>  
  
- <span data-ttu-id="9b04d-110">Metodo<xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="9b04d-110"><xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType> method.</span></span>  
  
- <span data-ttu-id="9b04d-111">Funzione [DebugBreak](/windows/win32/api/debugapi/nf-debugapi-debugbreak) (Win32).</span><span class="sxs-lookup"><span data-stu-id="9b04d-111">[DebugBreak](/windows/win32/api/debugapi/nf-debugapi-debugbreak) function (Win32).</span></span>  
  
 <span data-ttu-id="9b04d-112">Prima del .NET Framework 4, l'.NET Framework forniva chiavi del registro di sistema separate per controllare il comportamento dei debugger nativi e gestiti.</span><span class="sxs-lookup"><span data-stu-id="9b04d-112">Before the .NET Framework 4, the .NET Framework provided separate registry keys to control the behavior of native and managed debuggers.</span></span> <span data-ttu-id="9b04d-113">A partire da .NET Framework 4, il controllo viene consolidato in una singola chiave del registro di sistema: HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug.</span><span class="sxs-lookup"><span data-stu-id="9b04d-113">Starting with the .NET Framework 4, control is consolidated under a single registry key: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug.</span></span> <span data-ttu-id="9b04d-114">I valori che è possibile impostare per tale chiave determinano se un debugger viene richiamato e, in tal caso, se viene richiamato con una finestra di dialogo che richiede l'intervento dell'utente.</span><span class="sxs-lookup"><span data-stu-id="9b04d-114">The values you can set for that key determine whether a debugger is invoked, and, if so, whether it is invoked with a dialog box that requires user interaction.</span></span> <span data-ttu-id="9b04d-115">Per informazioni sull'impostazione di questa chiave del registro di sistema, vedere [configurazione del debug automatico](/windows/win32/debug/configuring-automatic-debugging).</span><span class="sxs-lookup"><span data-stu-id="9b04d-115">For information about setting this registry key, see [Configuring Automatic Debugging](/windows/win32/debug/configuring-automatic-debugging).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b04d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b04d-116">See also</span></span>

- [<span data-ttu-id="9b04d-117">Debug, traccia e profilatura</span><span class="sxs-lookup"><span data-stu-id="9b04d-117">Debugging, Tracing, and Profiling</span></span>](index.md)
- [<span data-ttu-id="9b04d-118">Semplificazione del debug di un'immagine</span><span class="sxs-lookup"><span data-stu-id="9b04d-118">Making an Image Easier to Debug</span></span>](making-an-image-easier-to-debug.md)
