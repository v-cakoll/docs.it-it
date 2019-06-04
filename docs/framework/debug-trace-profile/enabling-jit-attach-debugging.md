---
title: Attivazione dell'esecuzione del debug ad associazione JIT
ms.date: 03/30/2017
helpviewer_keywords:
- JIT-attach debugging
- debugging [.NET Framework], JIT-attach debugging
ms.assetid: f91fc5f7-de5a-4f23-b6ac-f450e63c662e
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 005395beabd956767b59e0cebd563fe883f6fe53
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489794"
---
# <a name="enabling-jit-attach-debugging"></a>Attivazione dell'esecuzione del debug ad associazione JIT
Il termine debug ad associazione JIT indica l'associazione di un debugger a un processo in caso di errori. Può anche essere attivato da specifici metodi o funzioni.  
  
 Il debug ad associazione JIT viene usato con le condizioni di errore seguenti:  
  
- Eccezioni non gestite (sia nel codice gestito che in quello nativo).  
  
- Metodo <xref:System.Environment.FailFast%2A?displayProperty=nameWithType> o funzione [RaiseFailFastException](https://go.microsoft.com/fwlink/?LinkId=182107) (famiglia Windows 7).  
  
- Errori irreversibili di runtime.  
  
 Il debug ad associazione JIT viene attivato anche dalle chiamate ai metodi e alle funzioni seguenti:  
  
- Metodo<xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> .  
  
- Metodo<xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType> .  
  
- Funzione [DebugBreak](https://go.microsoft.com/fwlink/?LinkId=182106) (Win32).  
  
 Prima di .NET Framework 4, .NET Framework non forniva chiavi del Registro di sistema separata per controllare il comportamento dei debugger nativi e gestiti. A partire da .NET Framework 4, controllo viene consolidato in una chiave del Registro di sistema singolo: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug. I valori che è possibile impostare per tale chiave determinano se un debugger viene richiamato e, in tal caso, se viene richiamato con una finestra di dialogo che richiede l'intervento dell'utente. Per informazioni sull'impostazione di questa chiave del Registro di sistema, vedere [configurazione del debug automatico](https://go.microsoft.com/fwlink/?LinkId=181767).  
  
## <a name="see-also"></a>Vedere anche

- [Debug, traccia e profilatura](../../../docs/framework/debug-trace-profile/index.md)
- [Semplificazione del debug di un'immagine](../../../docs/framework/debug-trace-profile/making-an-image-easier-to-debug.md)
