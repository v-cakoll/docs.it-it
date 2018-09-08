---
title: Attivazione dell'esecuzione del debug ad associazione JIT
ms.date: 03/30/2017
helpviewer_keywords:
- JIT-attach debugging
- debugging [.NET Framework], JIT-attach debugging
ms.assetid: f91fc5f7-de5a-4f23-b6ac-f450e63c662e
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b92592500f0babf29891710cedf1228b0ddcb0e4
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44208439"
---
# <a name="enabling-jit-attach-debugging"></a>Attivazione dell'esecuzione del debug ad associazione JIT
Il termine debug ad associazione JIT indica l'associazione di un debugger a un processo in caso di errori. Può anche essere attivato da specifici metodi o funzioni.  
  
 Il debug ad associazione JIT viene usato con le condizioni di errore seguenti:  
  
-   Eccezioni non gestite (sia nel codice gestito che in quello nativo).  
  
-   Metodo <xref:System.Environment.FailFast%2A?displayProperty=nameWithType> o funzione [RaiseFailFastException](https://go.microsoft.com/fwlink/?LinkId=182107) (famiglia Windows 7).  
  
-   Errori irreversibili di runtime.  
  
 Il debug ad associazione JIT viene attivato anche dalle chiamate ai metodi e alle funzioni seguenti:  
  
-   Metodo <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType>.  
  
-   Metodo <xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType>.  
  
-   Funzione [DebugBreak](https://go.microsoft.com/fwlink/?LinkId=182106) (Win32).  
  
 Prima di [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], .NET Framework forniva chiavi del Registro di sistema separate per controllare il comportamento dei debugger nativi e gestiti. A partire [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], il controllo viene consolidato in una singola chiave del Registro di sistema: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug. I valori che è possibile impostare per tale chiave determinano se un debugger viene richiamato e, in tal caso, se viene richiamato con una finestra di dialogo che richiede l'intervento dell'utente. Per informazioni sull'impostazione di questa chiave del Registro di sistema, vedere [configurazione del debug automatico](https://go.microsoft.com/fwlink/?LinkId=181767).  
  
## <a name="see-also"></a>Vedere anche  
 [Debug, traccia e profilatura](../../../docs/framework/debug-trace-profile/index.md)  
 [Semplificazione del debug di un'immagine](../../../docs/framework/debug-trace-profile/making-an-image-easier-to-debug.md)  
 [Abilitazione della funzione di profilatura](https://msdn.microsoft.com/library/3b669676-f0e0-4ebf-8674-68986dd2020d)
