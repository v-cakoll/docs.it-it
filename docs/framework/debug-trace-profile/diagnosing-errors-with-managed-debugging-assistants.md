---
title: Diagnostica degli errori tramite gli assistenti al debug gestito
ms.date: 08/14/2018
f1_keywords:
- EHMDA
helpviewer_keywords:
- run-time error debugging
- managed code, run-time debugging
- resource debugging
- registry, MDAs
- common language runtime, debugging
- MDAs (managed debugging assistants)
- configuration files [.NET Framework], debugging runtime events
- messages, managed debugging assistants
- application configuration files, managed debugging assistants
- debugging [.NET Framework], managed debugging assistants
- environment variables, MDAs
- access violation debugging [.NET Framework]
- diagnostics, managed debugging assistants
- unmanaged code, run-time debugging
- default debug output stream
- memory, debugging
- app.config files, managed debugging assistants
- managed debugging assistants (MDAs)
- debugging [.NET Framework], run-time errors
- trapping events
- runtime, error debugging
- disabling MDAs
- output, managed debugging assistants
- errors [.NET Framework], managed debugging assistants
ms.assetid: 76994ee6-9fa9-4059-b813-26578d24427c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b745fa6a78ab2a7ab0b3a94c9921883d3c56c1b7
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43532975"
---
# <a name="diagnose-errors-with-managed-debugging-assistants"></a>Diagnosticare gli errori di assistenti al debug gestito

Gli assistenti al debug gestito sono strumenti per il debug da usare insieme a CLR (Common Language Runtime) per fornire informazioni sullo stato del runtime. Gli assistenti generano messaggi informativi su eventi di runtime che non possono essere intercettati in altro modo. È possibile usare gli assistenti al debug gestito per isolare bug di applicazione difficili da individuare, che si verificano durante la transizione tra codice gestito e non gestito.

È possibile [Abilita o disabilita](#enable-and-disable-mdas) tutti assistenti al debug gestito aggiungendo una chiave nel Registro di sistema di Windows oppure impostando una variabile di ambiente. Le impostazioni di configurazione dell'applicazione permettono di abilitare assistenti al debug gestito specifici. È possibile definire impostazioni di configurazione aggiuntive per alcuni singoli assistenti al debug gestito nel file di configurazione dell'applicazione. Poiché questi file di configurazione sono analizzati durante il caricamento del runtime, è necessario abilitare l'assistente al debug gestito prima dell'avvio dell'applicazione gestita. Non è possibile abilitarlo per applicazioni già avviate.

La tabella seguente elenca gli assistenti al debug gestito forniti con .NET Framework:

|||
|-|-|
|[asynchronousThreadAbort](../../../docs/framework/debug-trace-profile/asynchronousthreadabort-mda.md)|[bindingFailure](../../../docs/framework/debug-trace-profile/bindingfailure-mda.md)|
|[callbackOnCollectedDelegate](../../../docs/framework/debug-trace-profile/callbackoncollecteddelegate-mda.md)|[contextSwitchDeadlock](../../../docs/framework/debug-trace-profile/contextswitchdeadlock-mda.md)|
|[dangerousThreadingAPI](../../../docs/framework/debug-trace-profile/dangerousthreadingapi-mda.md)|[dateTimeInvalidLocalFormat](../../../docs/framework/debug-trace-profile/datetimeinvalidlocalformat-mda.md)|
|[dirtyCastAndCallOnInterface](../../../docs/framework/debug-trace-profile/dirtycastandcalloninterface-mda.md)|[disconnectedContext](../../../docs/framework/debug-trace-profile/disconnectedcontext-mda.md)|
|[dllMainReturnsFalse](../../../docs/framework/debug-trace-profile/dllmainreturnsfalse-mda.md)|[exceptionSwallowedOnCallFromCom](../../../docs/framework/debug-trace-profile/exceptionswallowedoncallfromcom-mda.md)|
|[failedQI](../../../docs/framework/debug-trace-profile/failedqi-mda.md)|[fatalExecutionEngineError](../../../docs/framework/debug-trace-profile/fatalexecutionengineerror-mda.md)|
|[gcManagedToUnmanaged](../../../docs/framework/debug-trace-profile/gcmanagedtounmanaged-mda.md)|[gcUnmanagedToManaged](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)|
|[illegalPrepareConstrainedRegion](../../../docs/framework/debug-trace-profile/illegalprepareconstrainedregion-mda.md)|[invalidApartmentStateChange](../../../docs/framework/debug-trace-profile/invalidapartmentstatechange-mda.md)|
|[invalidCERCall](../../../docs/framework/debug-trace-profile/invalidcercall-mda.md)|[invalidFunctionPointerInDelegate](../../../docs/framework/debug-trace-profile/invalidfunctionpointerindelegate-mda.md)|
|[invalidGCHandleCookie](../../../docs/framework/debug-trace-profile/invalidgchandlecookie-mda.md)|[invalidIUnknown](../../../docs/framework/debug-trace-profile/invalidiunknown-mda.md)|
|[invalidMemberDeclaration](../../../docs/framework/debug-trace-profile/invalidmemberdeclaration-mda.md)|[invalidOverlappedToPinvoke](../../../docs/framework/debug-trace-profile/invalidoverlappedtopinvoke-mda.md)|
|[invalidVariant](../../../docs/framework/debug-trace-profile/invalidvariant-mda.md)|[jitCompilationStart](../../../docs/framework/debug-trace-profile/jitcompilationstart-mda.md)|
|[loaderLock](../../../docs/framework/debug-trace-profile/loaderlock-mda.md)|[loadFromContext](../../../docs/framework/debug-trace-profile/loadfromcontext-mda.md)|
|[marshalCleanupError](../../../docs/framework/debug-trace-profile/marshalcleanuperror-mda.md)|[marshaling](../../../docs/framework/debug-trace-profile/marshaling-mda.md)|
|[memberInfoCacheCreation](../../../docs/framework/debug-trace-profile/memberinfocachecreation-mda.md)|[moduloObjectHashcode](../../../docs/framework/debug-trace-profile/moduloobjecthashcode-mda.md)|
|[nonComVisibleBaseClass](../../../docs/framework/debug-trace-profile/noncomvisiblebaseclass-mda.md)|[notMarshalable](../../../docs/framework/debug-trace-profile/notmarshalable-mda.md)|
|[openGenericCERCall](../../../docs/framework/debug-trace-profile/opengenericcercall-mda.md)|[overlappedFreeError](../../../docs/framework/debug-trace-profile/overlappedfreeerror-mda.md)|
|[pInvokeLog](../../../docs/framework/debug-trace-profile/pinvokelog-mda.md)|[pInvokeStackImbalance](../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)|
|[raceOnRCWCleanup](../../../docs/framework/debug-trace-profile/raceonrcwcleanup-mda.md)|[reentrancy](../../../docs/framework/debug-trace-profile/reentrancy-mda.md)|
|[releaseHandleFailed](../../../docs/framework/debug-trace-profile/releasehandlefailed-mda.md)|[reportAvOnComRelease](../../../docs/framework/debug-trace-profile/reportavoncomrelease-mda.md)|
|[streamWriterBufferedDataLost](../../../docs/framework/debug-trace-profile/streamwriterbuffereddatalost-mda.md)|[virtualCERCall](../../../docs/framework/debug-trace-profile/virtualcercall-mda.md)|

Per impostazione predefinita, .NET Framework attiva un sottoinsieme di assistenti al debug gestito per tutti i debugger gestiti. È possibile visualizzare il set predefinito in Visual Studio, scegliendo **Windows** > **impostazioni eccezioni** sulla **Debug** menu e quindi espandendo il **Assistenti al debug gestito** elenco.

![Finestra Impostazioni eccezioni in Visual Studio](media/diagnosing-errors-with-managed-debugging-assistants/exception-settings-mdas.png)

## <a name="enable-and-disable-mdas"></a>Abilitare e disabilitare assistenti al debug gestito

È possibile abilitare e disabilitare gli assistenti al debug gestito usando una chiave del Registro di sistema, una variabile di ambiente e impostazioni di configurazione dell'applicazione. Per usare le impostazioni di configurazione dell'applicazione, è necessario abilitare la chiave del Registro di sistema o la variabile di ambiente.

> [!TIP]
> Anziché la disabilitazione di assistenti al debug gestito, è possibile impedire a Visual Studio di visualizzare la finestra di dialogo (MDA) ogni volta che viene ricevuta una notifica. A tale scopo, scegliere **Windows** > **impostazioni eccezioni** sulla **Debug** menu, espandere il **assistenti al debug gestito**visualizzare un elenco e quindi selezionare o deselezionare il **Interrompi se generata** casella di controllo per il singolo assistente al debug gestito.

### <a name="registry-key"></a>Chiave del Registro di sistema

Per abilitare assistenti al debug gestito, aggiungere il **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework\MDA** sottochiave (tipo REG_SZ, valore 1) nel Registro di sistema Windows. Copiare l'esempio seguente in un file di testo denominato *MDAEnable. reg*. Aprire l'Editor del Registro di sistema di Windows (RegEdit.exe) e dal **File** dal menu **importazione**. Selezionare il *MDAEnable. reg* file per abilitare assistenti al debug gestito in tale computer. Imposta la sottochiave sul valore di stringa pari **1** (non il valore DWORD pari **1**) consente la lettura delle impostazioni dell'Assistente al debug gestito dal *NomeApplicazione*. mda. config file. Ad esempio, il file di configurazione MDA per il blocco note verrebbe denominato Blocconote.

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework]
"MDA"="1"
```

Se il computer esegue un'applicazione a 32 bit in un sistema operativo a 64 bit, la chiave dell'assistente al debug gestito deve essere configurata come segue:

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework]
"MDA"="1"
```

Visualizzare [le impostazioni di configurazione specifiche dell'applicazione](#application-specific-configuration-settings) per altre informazioni. L'impostazione del Registro di sistema può essere sostituita dalla variabile di ambiente COMPLUS_MDA. Visualizzare [variabile di ambiente](#environment-variable) per altre informazioni.

Per disabilitare assistenti al debug gestito, impostare la sottochiave relativa a MDA su **0** (zero) usando l'Editor del Registro di sistema di Windows.

Per impostazione predefinita, alcuni assistenti al debug gestito sono abilitati quando si esegue un'applicazione associata a un debugger, anche se non si aggiunge la chiave del Registro di sistema, È possibile disabilitare questi assistenti eseguendo il *MDADisable. reg* file come descritto in precedenza in questa sezione.

### <a name="environment-variable"></a>Variabile di ambiente

L'attivazione dell'assistente al debug gestito può essere controllata anche dalla variabile di ambiente COMPLUS_MDA, che sostituisce la chiave del Registro di sistema. La stringa COMPLUS_MDA è un elenco di nomi di assistenti al debug gestito o di altre stringhe di controllo speciali delimitato da punto e virgola e in cui non è applicata la distinzione tra maiuscole/minuscole. L'avvio con un debugger gestito o non gestito abilita un set di assistenti al debug gestito per impostazione predefinita, aggiungendo in modo implicito l'elenco delimitato da punto e virgola di assistenti al debug gestito abilitati per impostazione predefinita con i debugger davanti al valore della variabile di ambiente o della chiave del Registro di sistema. Di seguito sono elencate le stringhe di controllo speciali:

- `0` - Disattiva tutti gli assistenti al debug gestito.

- `1`: legge le impostazioni dell'assistente al debug gestito da *NomeApplicazione*.mda.config.

- `managedDebugger` - Attiva esplicitamente tutti gli assistenti al debug gestito attivati in modo implicito quando si avvia un eseguibile gestito con un debugger.

- `unmanagedDebugger` - Attiva esplicitamente tutti gli assistenti al debug gestito attivati in modo implicito quando si avvia un eseguibile non gestito con un debugger.

In caso di conflitto, le impostazioni più recenti eseguono l'override di quelle precedenti:

- `COMPLUS_MDA=0` disabilita tutti gli assistenti al debug gestito, inclusi quelli abilitati in modo implicito con un debugger.

- `COMPLUS_MDA=gcUnmanagedToManaged` abilita `gcUnmanagedToManaged`, oltre a eventuali assistenti al debug gestito abilitati in modo implicito con un debugger.

- `COMPLUS_MDA=0;gcUnmanagedToManaged` abilita `gcUnmanagedToManaged` ma disabilita gli assistenti al debug gestito che sarebbero altrimenti abilitati in modo implicito con un debugger.

### <a name="application-specific-configuration-settings"></a>Impostazioni di configurazione specifiche dell'applicazione

È possibile abilitare, disabilitare e configurare individualmente alcuni assistenti nel file di configurazione MDA per l'applicazione. Per abilitare l'uso di un file di configurazione dell'applicazione al fine di configurare gli assistenti al debug gestito, è necessario impostare la chiave del Registro di sistema relativa a MDA o la variabile di ambiente COMPLUS_MDA. Il file di configurazione dell'applicazione si trova in genere nella stessa directory del file eseguibile (con estensione exe) dell'applicazione. Il formato del nome del file è *NomeApplicazione*.mda.config. Ad esempio, blocconote.exe.mda.config. Gli assistenti abilitati nel file di configurazione dell'applicazione potrebbero disporre di attributi o elementi progettati in modo specifico per il controllo del comportamento dell'assistente.

Nell'esempio seguente viene illustrato come abilitare e configurare il [marshalling](../../../docs/framework/debug-trace-profile/marshaling-mda.md):

```xml
<mdaConfig>
  <assistants>
    <marshaling>
      <methodFilter>
        <match name="*"/>
      </methodFilter>
      <fieldFilter>
        <match name="*"/>
      </fieldFilter>
    </marshaling>
  </assistants>
</mdaConfig>
```

L'assistente `Marshaling` emette informazioni sul tipo gestito di cui si sta eseguendo il marshalling a un tipo non gestito per ogni transizione da gestito a non gestito nell'applicazione. Il `Marshaling` assistente al debug gestito può anche filtrare i nomi del metodo e campi della struttura forniti nel **methodFilter** e **fieldFilter** elementi figlio, rispettivamente.

Nell'esempio seguente viene illustrato come abilitare più assistenti al debug gestito usando le rispettive impostazioni predefinite:

```xml
<mdaConfig>
  <assistants>
    <illegalPrepareConstrainedRegion />
    <invalidCERCall />
    <openGenericCERCall />
    <virtualCERCall />
  </assistants>
</mdaConfig>
```

> [!IMPORTANT]
> Se si specifica più di un assistente in un file di configurazione, è necessario elencarli in ordine alfabetico. Ad esempio, per abilitare gli assistenti `virtualCERCall` e `invalidCERCall`, è necessario aggiungere la voce `<invalidCERCall />` prima della voce `<virtualCERCall />`. Se le voci non sono in ordine alfabetico, sarà visualizzato un messaggio relativo a un'eccezione non gestita per file di configurazione non valido.

## <a name="mda-exceptions"></a>Eccezioni (MDA)

Quando un assistente al debug gestito è abilitata, è attiva anche quando il codice non è in esecuzione in un debugger. Se un evento dell'assistente al debug gestito è generato quando non è presente alcun debugger, il messaggio relativo all'evento è visualizzato in una finestra di dialogo per eccezioni non gestite, anche se non si tratta di un'eccezione non gestita. Per evitare la visualizzazione della finestra di dialogo, rimuovere l'impostazione per l'abilitazione dell'assistente al debug gestito quando il codice non è in esecuzione in un ambiente di debug.

Quando il codice viene eseguito nell'ambiente di sviluppo integrato (IDE) di Visual Studio, è possibile evitare la finestra di dialogo di eccezione che viene visualizzata per eventi assistente al debug gestito specifici. A tale scopo, scegliere il **Debug** menu, scegliere **Windows** > **impostazioni eccezioni**. Nel **impostazioni eccezioni** finestra, espandere il **assistenti al debug gestito** elenco e quindi deselezionare le **Interrompi se generata** casella di controllo per il singolo assistente al debug gestito. È anche possibile usare questa finestra di dialogo per *abilitare* la visualizzazione delle finestre di dialogo di eccezione assistente al debug gestito.

## <a name="mda-output"></a>Output degli assistenti al debug gestito

MDA output è simile all'esempio seguente, che mostra l'output di `PInvokeStackImbalance` assistente al debug gestito:

**Una chiamata alla funzione di PInvoke ' MDATest! MDATest.Program::StdCall' ha abbia sbilanciato lo stack. È probabile che la firma PInvoke gestita non corrisponde alla firma di destinazione non gestita. Verificare che la convenzione di chiamata e i parametri della firma PInvoke corrispondono alla firma non gestita di destinazione.**

## <a name="see-also"></a>Vedere anche

- [Debug, traccia e profilatura](../../../docs/framework/debug-trace-profile/index.md)
