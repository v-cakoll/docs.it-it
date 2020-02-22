---
title: Accesso con privilegi elevati per comandi dotnet
description: Informazioni sulle procedure consigliate per comandi dotnet che richiedono l'accesso con privilegi elevati.
author: wli3
ms.date: 06/26/2019
ms.openlocfilehash: fe33cbe966d175f71ba350737b283c1e83f64fa6
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543430"
---
# <a name="elevated-access-for-dotnet-commands"></a>Accesso con privilegi elevati per comandi dotnet

Le procedure consigliate per lo sviluppo di software supportano gli sviluppatori nella scrittura di software con una richiesta minima di privilegi. Per alcuni software, ad esempio gli strumenti di monitoraggio delle prestazioni, è però necessaria un'autorizzazione di amministratore a causa delle regole del sistema operativo. Questo documento descrive gli scenari supportati per la scrittura di questo tipo di software usando .NET Core. 

I comandi seguenti possono essere eseguiti con privilegi elevati:

- Comandi `dotnet tool`, ad esempio [dotnet tool install](dotnet-tool-install.md).
- `dotnet run --no-build`

Non è consigliabile eseguire altri comandi con privilegi elevati. In particolare, non è consigliabile elevare i privilegi con comandi che usano MSBuild, ad esempio [dotnet restore](dotnet-restore.md), [dotnet build](dotnet-build.md) e [dotnet run](dotnet-run.md). Il problema principale è la gestione delle autorizzazioni, quando un utente passa da account radice ad account con restrizioni dopo l'invio di comandi dotnet. Può succedere che un utente con restrizioni non acceda al file creato da un utente ROOT. Questa situazione può essere risolta in diversi modi che non è necessario analizzare per primi.

È possibile eseguire comandi come radice, purché l'utente non passi da account radice ad account con restrizioni. I contenitori Docker vengono ad esempio eseguiti come radice per impostazione predefinita, pertanto hanno questa caratteristica.

## <a name="global-tool-installation"></a>Installazione dello strumento globale

Le istruzioni seguenti illustrano il modo consigliato per installare, eseguire e disinstallare gli strumenti per .NET Core che per essere eseguiti richiedono autorizzazioni con privilegi elevati.

<!-- markdownlint-disable MD025 -->

# <a name="windows"></a>[Windows](#tab/windows)

### <a name="install-the-tool"></a>Installare lo strumento

Se la cartella `%ProgramFiles%\dotnet-tools` è già esistente, eseguire le operazioni seguenti per verificare se il gruppo "Utenti" dispone dell'autorizzazione per scrivere o modificare tale directory:

- Fare clic con il pulsante destro del mouse sulla cartella `%ProgramFiles%\dotnet-tools` e selezionare **Proprietà**. Verrà visualizzata la finestra di dialogo **Proprietà comuni**. 
- Selezionare la scheda **sicurezza** . In utenti e **gruppi**controllare se il gruppo "utenti" dispone dell'autorizzazione per scrivere o modificare la directory. 
- Se il gruppo "Utenti" è autorizzato alla scrittura o alla modifica della directory, usare un nome di directory diverso quando si installano gli strumenti anziché usare *dotnet-tools*.

Per installare gli strumenti, eseguire il comando seguente al prompt con privilegi elevati. Verrà creata la cartella *dotnet-tools* durante l'installazione.

```dotnetcli
dotnet tool install PACKAGEID --tool-path "%ProgramFiles%\dotnet-tools".
```

### <a name="run-the-global-tool"></a>Eseguire lo strumento globale

**Opzione 1**: usare il percorso completo al prompt con privilegi elevati:

```cmd
"%ProgramFiles%\dotnet-tools\TOOLCOMMAND"
```

**Opzione 2**: aggiungere la cartella appena creata a `%Path%`. È necessario eseguire questa operazione una sola volta.

```cmd
setx Path "%Path%;%ProgramFiles%\dotnet-tools\"
```

Eseguire con il comando seguente:

```cmd
TOOLCOMMAND
```

### <a name="uninstall-the-global-tool"></a>Disinstallare lo strumento globale

Al prompt con privilegi elevati digitare il comando seguente:

```dotnetcli
dotnet tool uninstall PACKAGEID --tool-path "%ProgramFiles%\dotnet-tools"
```

# <a name="linux"></a>[Linux](#tab/linux)

[!INCLUDE [elevated-access-unix](../../../includes/elevated-access-unix.md)]

# <a name="macos"></a>[macOS](#tab/macos)

[!INCLUDE [elevated-access-unix](../../../includes/elevated-access-unix.md)]

---

## <a name="local-tools"></a>Strumenti locali

L'ambito degli strumenti locali è definito in base ad albero di sottodirectory e utente. Quando vengono eseguiti con privilegi elevati, gli strumenti locali condividono un ambiente utente con restrizioni nell'ambiente con privilegi elevati. In Linux e macOS i file vengono di conseguenza impostati con accesso riservato solo all'utente ROOT. Se l'utente passa nuovamente a un account con restrizioni, l'utente non potrà più accedere o scrivere i file. Non è quindi consigliato installare strumenti che richiedono elevazione come gli strumenti locali. Usare invece l'opzione `--tool-path` e seguire le linee guida precedenti per gli strumenti globali.

## <a name="elevation-during-development"></a>Elevazione durante lo sviluppo

Durante lo sviluppo potrebbe essere necessario l'accesso con privilegi elevati per testare l'applicazione. Questo scenario è ad esempio comune per le app IoT. È consigliabile compilare l'applicazione senza elevazione ed eseguirla poi elevando i privilegi. Esistono alcuni modelli come quelli riportati di seguito:

- Uso di un eseguibile generato, che offre le prestazioni migliori in fase di avvio:

   ```dotnetcli
   dotnet build
   sudo ./bin/Debug/netcoreapp3.0/APPLICATIONNAME
   ```
    
- Uso del comando [dotnet run](dotnet-run.md) con il flag `—no-build` per evitare di generare nuovi file binari:

   ```dotnetcli
   dotnet build
   sudo dotnet run --no-build
   ```

## <a name="see-also"></a>Vedere anche

- [Panoramica degli strumenti globali .NET Core](global-tools.md)
