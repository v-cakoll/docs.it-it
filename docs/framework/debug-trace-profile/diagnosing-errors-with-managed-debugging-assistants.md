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
ms.openlocfilehash: 712fbbe9e0ad291385e8eef321c5e8a2fa092a5d
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216562"
---
# <a name="diagnose-errors-with-managed-debugging-assistants"></a>Diagnosticare gli errori con gli assistenti al debug gestito

Gli assistenti al debug gestito sono strumenti per il debug da usare insieme a CLR (Common Language Runtime) per fornire informazioni sullo stato del runtime. Gli assistenti generano messaggi informativi su eventi di runtime che non possono essere intercettati in altro modo. È possibile usare gli assistenti al debug gestito per isolare bug di applicazione difficili da individuare, che si verificano durante la transizione tra codice gestito e non gestito.

È possibile [abilitare o disabilitare](#enable-and-disable-mdas) tutti i MDA aggiungendo una chiave al registro di sistema di Windows o impostando una variabile di ambiente. Le impostazioni di configurazione dell'applicazione permettono di abilitare assistenti al debug gestito specifici. È possibile definire impostazioni di configurazione aggiuntive per alcuni singoli assistenti al debug gestito nel file di configurazione dell'applicazione. Poiché questi file di configurazione sono analizzati durante il caricamento del runtime, è necessario abilitare l'assistente al debug gestito prima dell'avvio dell'applicazione gestita. Non è possibile abilitarlo per applicazioni già avviate.

Nella tabella seguente sono elencati i MDA forniti con la .NET Framework:

|||
|-|-|
|[asynchronousThreadAbort](asynchronousthreadabort-mda.md)|[bindingFailure](bindingfailure-mda.md)|
|[callbackOnCollectedDelegate](callbackoncollecteddelegate-mda.md)|[contextSwitchDeadlock](contextswitchdeadlock-mda.md)|
|[dangerousThreadingAPI](dangerousthreadingapi-mda.md)|[dateTimeInvalidLocalFormat](datetimeinvalidlocalformat-mda.md)|
|[dirtyCastAndCallOnInterface](dirtycastandcalloninterface-mda.md)|[disconnectedContext](disconnectedcontext-mda.md)|
|[dllMainReturnsFalse](dllmainreturnsfalse-mda.md)|[exceptionSwallowedOnCallFromCom](exceptionswallowedoncallfromcom-mda.md)|
|[failedQI](failedqi-mda.md)|[fatalExecutionEngineError](fatalexecutionengineerror-mda.md)|
|[gcManagedToUnmanaged](gcmanagedtounmanaged-mda.md)|[gcUnmanagedToManaged](gcunmanagedtomanaged-mda.md)|
|[illegalPrepareConstrainedRegion](illegalprepareconstrainedregion-mda.md)|[invalidApartmentStateChange](invalidapartmentstatechange-mda.md)|
|[invalidCERCall](invalidcercall-mda.md)|[invalidFunctionPointerInDelegate](invalidfunctionpointerindelegate-mda.md)|
|[invalidGCHandleCookie](invalidgchandlecookie-mda.md)|[invalidIUnknown](invalidiunknown-mda.md)|
|[invalidMemberDeclaration](invalidmemberdeclaration-mda.md)|[invalidOverlappedToPinvoke](invalidoverlappedtopinvoke-mda.md)|
|[invalidVariant](invalidvariant-mda.md)|[jitCompilationStart](jitcompilationstart-mda.md)|
|[loaderLock](loaderlock-mda.md)|[loadFromContext](loadfromcontext-mda.md)|
|[marshalCleanupError](marshalcleanuperror-mda.md)|[marshaling](marshaling-mda.md)|
|[memberInfoCacheCreation](memberinfocachecreation-mda.md)|[moduloObjectHashcode](moduloobjecthashcode-mda.md)|
|[nonComVisibleBaseClass](noncomvisiblebaseclass-mda.md)|[notMarshalable](notmarshalable-mda.md)|
|[openGenericCERCall](opengenericcercall-mda.md)|[overlappedFreeError](overlappedfreeerror-mda.md)|
|[pInvokeLog](pinvokelog-mda.md)|[pInvokeStackImbalance](pinvokestackimbalance-mda.md)|
|[raceOnRCWCleanup](raceonrcwcleanup-mda.md)|[reentrancy](reentrancy-mda.md)|
|[releaseHandleFailed](releasehandlefailed-mda.md)|[reportAvOnComRelease](reportavoncomrelease-mda.md)|
|[streamWriterBufferedDataLost](streamwriterbuffereddatalost-mda.md)|[virtualCERCall](virtualcercall-mda.md)|

Per impostazione predefinita, .NET Framework attiva un sottoinsieme di assistenti al debug gestito per tutti i debugger gestiti. È possibile visualizzare il set predefinito in Visual Studio scegliendo **Windows** > **Impostazioni eccezioni** dal menu **debug** , quindi espandendo l'elenco **assistenti al debug gestito** .

![Finestra Impostazioni eccezioni in Visual Studio](./media/diagnosing-errors-with-managed-debugging-assistants/exception-settings-mdas.png)

## <a name="enable-and-disable-mdas"></a>Abilitare e disabilitare MDA

È possibile abilitare e disabilitare gli assistenti al debug gestito usando una chiave del Registro di sistema, una variabile di ambiente e impostazioni di configurazione dell'applicazione. Per usare le impostazioni di configurazione dell'applicazione, è necessario abilitare la chiave del Registro di sistema o la variabile di ambiente.

> [!TIP]
> Anziché disabilitare MDA, è possibile impedire a Visual Studio di visualizzare la finestra di dialogo MDA ogni volta che viene ricevuta una notifica dell'assistente al debug gestito. A tale scopo, scegliere **Windows** > **Impostazioni eccezioni** dal menu **debug** , espandere l'elenco **assistenti al debug gestito** e quindi selezionare o deselezionare la casella di controllo **Interrompi quando viene generata** per il singolo assistente al debug gestito.

### <a name="registry-key"></a>Chiave del Registro

Per abilitare MDA, aggiungere il **\\HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft.** Sottochiave NETFramework\MDA (tipo REG_SZ, valore 1) nel registro di sistema di Windows. Copiare l'esempio seguente in un file di testo denominato *MDAEnable. reg*. Aprire l'editor del registro di sistema di Windows (RegEdit. exe) e scegliere **Importa**dal menu **file** . Selezionare il file *MDAEnable. reg* per abilitare MDA nel computer. Se si imposta la sottochiave sul valore stringa **1** (non DWORD valore **1**), viene abilitata la lettura delle impostazioni dell'assistente al debug gestito dal file *ApplicationName. suffiss*. mda. config. Il file di configurazione dell'assistente al debug gestito per il blocco note, ad esempio, è denominato Notepad. exe. mda. config.

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

Per ulteriori informazioni, vedere [impostazioni di configurazione specifiche dell'applicazione](#application-specific-configuration-settings) . L'impostazione del Registro di sistema può essere sostituita dalla variabile di ambiente COMPLUS_MDA. Per ulteriori informazioni, vedere [variabile di ambiente](#environment-variable) .

Per disabilitare MDA, impostare la sottochiave MDA su **0** (zero) utilizzando l'editor del registro di sistema di Windows.

Per impostazione predefinita, alcuni assistenti al debug gestito sono abilitati quando si esegue un'applicazione associata a un debugger, anche se non si aggiunge la chiave del Registro di sistema, È possibile disabilitare questi assistenti eseguendo il file *MDADisable. reg* come descritto in precedenza in questa sezione.

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

È possibile abilitare, disabilitare e configurare individualmente alcuni assistenti nel file di configurazione MDA per l'applicazione. Per abilitare l'uso di un file di configurazione dell'applicazione al fine di configurare gli assistenti al debug gestito, è necessario impostare la chiave del Registro di sistema relativa a MDA o la variabile di ambiente COMPLUS_MDA. Il file di configurazione dell'applicazione si trova in genere nella stessa directory del file eseguibile (con estensione exe) dell'applicazione. Il nome del file assume il formato *ApplicationName*. mda. config; ad esempio, Notepad. exe. mda. config. Gli assistenti abilitati nel file di configurazione dell'applicazione possono disporre di attributi o elementi appositamente progettati per controllare il comportamento dell'assistente.

Nell'esempio seguente viene illustrato come abilitare e configurare il [marshalling](marshaling-mda.md):

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

L'assistente `Marshaling` emette informazioni sul tipo gestito di cui si sta effettuando il marshalling a un tipo non gestito per ogni transizione da gestito a non gestito nell'applicazione. Il `Marshaling` MDA consente inoltre di filtrare i nomi dei campi del metodo e della struttura forniti rispettivamente negli elementi figlio **methodFilter** e **fieldFilter** .

Nell'esempio seguente viene illustrato come abilitare più MDA utilizzando le impostazioni predefinite:

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

## <a name="mda-exceptions"></a>Eccezioni MDA

Quando un assistente al debug gestito è abilitato, è attivo anche quando il codice non è in esecuzione in un debugger. Se un evento dell'assistente al debug gestito è generato quando non è presente alcun debugger, il messaggio relativo all'evento è visualizzato in una finestra di dialogo per eccezioni non gestite, anche se non si tratta di un'eccezione non gestita. Per evitare la visualizzazione della finestra di dialogo, rimuovere l'impostazione per l'abilitazione dell'assistente al debug gestito quando il codice non è in esecuzione in un ambiente di debug.

Quando il codice viene eseguito nell'IDE di Visual Integrated Development Environment studio, è possibile evitare la finestra di dialogo di eccezione visualizzata per eventi di assistente al debug gestito specifici. A tale scopo, scegliere **Windows** > **Impostazioni eccezioni**dal menu **debug** . Nella finestra **Impostazioni eccezioni** espandere l'elenco **assistenti al debug gestito** , quindi deselezionare la casella di controllo **Interrompi quando generata** per il singolo assistente al debug gestito. È inoltre possibile utilizzare questa finestra di dialogo per *abilitare* la visualizzazione delle finestre di dialogo delle eccezioni dell'assistente al debug gestito.

## <a name="mda-output"></a>Output degli assistenti al debug gestito

L'output dell'assistente al debug gestito è simile all'esempio seguente, che mostra l'output del `PInvokeStackImbalance` MDA:

**Una chiamata alla funzione PInvoke ' MDATest!' MDATest. Program:: StdCall ' ha sbilanciato lo stack. Questa operazione è probabilmente dovuta al fatto che la firma PInvoke gestita non corrisponde alla firma di destinazione non gestita. Verificare che la convenzione di chiamata e i parametri della firma PInvoke corrispondano alla firma non gestita di destinazione.**

## <a name="see-also"></a>Vedere anche

- [Debug, analisi e profilatura](index.md)
