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
# <a name="enabling-jit-attach-debugging"></a>Attivazione dell'esecuzione del debug ad associazione JIT
Il termine debug ad associazione JIT indica l'associazione di un debugger a un processo in caso di errori. Può anche essere attivato da specifici metodi o funzioni.  
  
 Il debug ad associazione JIT viene usato con le condizioni di errore seguenti:  
  
- Eccezioni non gestite (sia nel codice gestito che in quello nativo).  
  
- Metodo <xref:System.Environment.FailFast%2A?displayProperty=nameWithType> o funzione [RaiseFailFastException](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raisefailfastexception) (famiglia Windows 7).  
  
- Errori irreversibili di runtime.  
  
 Il debug ad associazione JIT viene attivato anche dalle chiamate ai metodi e alle funzioni seguenti:  
  
- Metodo<xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> .  
  
- Metodo<xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType> .  
  
- Funzione [DebugBreak](/windows/win32/api/debugapi/nf-debugapi-debugbreak) (Win32).  
  
 Prima del .NET Framework 4, l'.NET Framework forniva chiavi del registro di sistema separate per controllare il comportamento dei debugger nativi e gestiti. A partire da .NET Framework 4, il controllo viene consolidato in una singola chiave del registro di sistema: HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug. I valori che è possibile impostare per tale chiave determinano se un debugger viene richiamato e, in tal caso, se viene richiamato con una finestra di dialogo che richiede l'intervento dell'utente. Per informazioni sull'impostazione di questa chiave del registro di sistema, vedere [configurazione del debug automatico](/windows/win32/debug/configuring-automatic-debugging).  
  
## <a name="see-also"></a>Vedere anche

- [Debug, traccia e profilatura](index.md)
- [Semplificazione del debug di un'immagine](making-an-image-easier-to-debug.md)
