---
title: Thread in primo piano e in background
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], foreground
- threading [.NET Framework], background
- foreground threads
- background threads
ms.assetid: cfe0d632-dd35-47e0-91ad-f742a444005e
ms.openlocfilehash: 5e7ec9e2c2a5ba3de1b4518cea15eb5f512640d3
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84279685"
---
# <a name="foreground-and-background-threads"></a>Thread in primo piano e in background
Un thread gestito è un thread in background o un thread in primo piano. I thread in background sono identici ai thread in primo piano con un'unica eccezione: un thread in background non mantiene in esecuzione l'ambiente di esecuzione gestito. Dopo che tutti i thread in primo piano sono stati arrestati in un processo gestito (in cui il file EXE è un assembly gestito), il sistema arresta tutti i thread in background e si arresta.  
  
> [!NOTE]
> Quando il runtime arresta un thread in background perché è in corso l'arresto del processo, non vengono generate eccezioni nel thread. Quando tuttavia i thread vengono arrestati perché il metodo <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> scarica il dominio dell'applicazione, viene generata un'eccezione <xref:System.Threading.ThreadAbortException> nei thread in primo piano e in background.  
  
 Usare la proprietà <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType> per determinare se un thread è un thread in background o in primo piano oppure per modificarne lo stato. Un thread può essere sostituito con un thread in background in qualsiasi momento impostandone la proprietà <xref:System.Threading.Thread.IsBackground%2A> su `true`.  
  
> [!IMPORTANT]
> Lo stato di primo piano o di background di un thread non interessa l'esito di un'eccezione non gestita nel thread. In .NET Framework versione 2.0 un'eccezione non gestita nei thread in primo piano o in background comporta la terminazione dell'applicazione. Vedere [Eccezioni in thread gestiti](exceptions-in-managed-threads.md).  
  
 I thread che appartengono al pool di thread gestiti (ovvero, i thread la cui proprietà <xref:System.Threading.Thread.IsThreadPoolThread%2A> è `true`) sono thread in background. Tutti i thread che accedono all'ambiente di esecuzione gestito dal codice non gestito sono contrassegnati come thread in background. Tutti i thread generati creando e avviando un nuovo oggetto <xref:System.Threading.Thread> sono thread in primo piano per impostazione predefinita.  
  
 Se si usa un thread per monitorare un'attività, ad esempio una connessione socket, impostarne la proprietà <xref:System.Threading.Thread.IsBackground%2A> su `true` in modo che il thread non impedisca la terminazione del processo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType>
- <xref:System.Threading.Thread>
- <xref:System.Threading.ThreadAbortException>
