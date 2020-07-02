---
ms.openlocfilehash: 0237c848d71150aaea1f9de4f4b16a0cbbc4ab3a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615667"
---
### <a name="new-64-bit-jit-compiler-in-the-net-framework-46"></a>Nuovo compilatore JIT a 64 bit in .NET Framework 4.6

#### <a name="details"></a>Dettagli

A partire da .NET Framework 4.6, viene usato un nuovo compilatore JIT a 64 bit per la compilazione JIT. In alcuni casi, viene generata un'eccezione imprevista o si nota un comportamento diverso rispetto all'esecuzione di un'app con il compilatore a 32 bit o il compilatore precedente JIT a 64 bit. Questa modifica non influisce sul compilatore JIT a 32 bit. Le differenze note includono quanto segue:

- In determinate condizioni, un'operazione di conversione unboxing può generare <xref:System.NullReferenceException> nelle build di rilascio con l'ottimizzazione attivata.
- In alcuni casi l'esecuzione del codice di produzione in un corpo del metodo di grandi dimensioni può generare <xref:System.StackOverflowException>.
- In determinate condizioni, le strutture passate a un metodo vengono considerate come tipi riferimento piuttosto che tipi valore nelle build di versione. Una delle manifestazioni di questo problema è che i singoli elementi in una raccolta vengono visualizzati in un ordine imprevisto.
- In determinate condizioni, il confronto dei valori di <xref:System.UInt16> con il set di bit elevato non è corretto se l'ottimizzazione è abilitata.
- In determinate condizioni, in particolare durante l'inizializzazione dei valori della matrice, è possibile che l'inizializzazione della memoria con l'istruzione IL <xref:System.Reflection.Emit.OpCodes.Initblk?displayProperty=nameWithType> venga eseguita con un valore non corretto. Ciò può generare un'eccezione non gestita o un output non corretto.
- In alcuni casi rari, un test condizionale dei bit può restituire il valore <xref:System.Boolean> non corretto o generare un'eccezione se sono abilitate le ottimizzazioni del compilatore.
- In determinate condizioni, se un'istruzione `if` viene usata per testare una condizione prima di immettere un blocco `try` e in uscita dal blocco `try`, e la stessa condizione viene valutata nel blocco `catch` o `finally`, il nuovo compilatore JIT a 64 bit rimuove la condizione `if` dal blocco `catch` o `finally` quando ottimizza il codice. Di conseguenza, il codice contenuto nell'istruzione `if` nel blocco `catch` o `finally` viene eseguita in modo non condizionale.

#### <a name="suggestion"></a>Suggerimento

**Mitigazione dei problemi noti** <br/> Se si verificano i problemi elencati in precedenza, è possibile risolverli effettuando una delle operazioni seguenti:

- Eseguire l'aggiornamento a .NET Framework 4.6.2. Il nuovo compilatore a 64 bit incluso in .NET Framework 4.6.2 risolve tutti questi problemi noti.
- Assicurarsi che la versione di Windows venga aggiornata tramite l'esecuzione di Windows Update. Gli aggiornamenti dei servizi per .NET Framework 4.6 e 4.6.1 risolvono tutti questi problemi, ad eccezione di <xref:System.NullReferenceException> in un'operazione di conversione unboxing.
- Eseguire la compilazione con la versione precedente del compilatore JIT a 64 bit. Vedere la sezione **Mitigazione di altri problemi** per altre informazioni su come eseguire questa operazione.
**Mitigazione di altri problemi** <br/> Nel caso di qualsiasi altra differenza nel comportamento tra il codice compilato con la versione precedente del compilatore a 64 bit e quello compilato con la versione nuova, oppure tra le versioni di debug e rilascio dell'app compilate entrambe con il nuovo compilatore JIT a 64 bit, è possibile eseguire le operazioni seguenti per compilare l'app con la versione precedente del compilatore JIT a 64 bit:

- Per ogni singola applicazione, è possibile aggiungere l' [<](~/docs/framework/configure-apps/file-schema/runtime/uselegacyjit-element.md) elemento al file di configurazione dell'applicazione. Le operazioni seguenti consentono di disattivare la compilazione con il nuovo compilatore JIT a 64 bit e usare invece il compilatore JIT a 64 bit legacy.

    ```xml
    <?xml version ="1.0"?>
    <configuration>
      <runtime>
       <useLegacyJit enabled="1" />
      </runtime>
    </configuration>
    ```

- Per ogni utente è possibile aggiungere un valore `REG_DWORD` denominato `useLegacyJit` per la chiave `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` del Registro di sistema. Il valore 1 abilita il compilatore JIT a 64 bit legacy, mentre il valore 0 lo disattiva e consente di abilitare il nuovo compilatore JIT a 64 bit.
- Per ogni macchina è possibile aggiungere un valore `REG_DWORD` denominato `useLegacyJit` per la chiave `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` del Registro di sistema. Il valore `1` abilita il compilatore JIT a 64 bit legacy, mentre il valore `0` lo disabilita e consente di abilitare il nuovo compilatore JIT a 64 bit.
È possibile inoltre inviare i dettagli sul problema segnalando un bug in [Microsoft Connect](https://connect.microsoft.com/VisualStudio).

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| Version | 4.6         |
| Type    | Ridestinazione |
