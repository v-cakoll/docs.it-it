---
title: Attivazione dell'esecuzione del debug ad associazione JIT
ms.date: 03/30/2017
helpviewer_keywords:
- JIT-attach debugging
- debugging [.NET Framework], JIT-attach debugging
ms.assetid: f91fc5f7-de5a-4f23-b6ac-f450e63c662e
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f4d4e2b3806d2c4d84b59e1cd44eb03ab7b278c9
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052831"
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
  
 Prima del .NET Framework 4, l'.NET Framework forniva chiavi del registro di sistema separate per controllare il comportamento dei debugger nativi e gestiti. A partire da .NET Framework 4, il controllo viene consolidato in una singola chiave del registro di sistema: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug. I valori che è possibile impostare per tale chiave determinano se un debugger viene richiamato e, in tal caso, se viene richiamato con una finestra di dialogo che richiede l'intervento dell'utente. Per informazioni sull'impostazione di questa chiave del registro di sistema, vedere [configurazione del debug automatico](https://go.microsoft.com/fwlink/?LinkId=181767).  
  
## <a name="see-also"></a>Vedere anche

- [Debug, traccia e profilatura](index.md)
- [Semplificazione del debug di un'immagine](making-an-image-easier-to-debug.md)
