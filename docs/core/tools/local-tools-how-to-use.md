---
title: 'Esercitazione: Installare e usare gli strumenti locali .NET CoreTutorial: Install and use .NET Core local tools'
description: Informazioni su come installare e usare uno strumento .NET come strumento locale.
ms.date: 02/12/2020
ms.openlocfilehash: a4355886513040e2436bdbd87905e5baee2dd7a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78156699"
---
# <a name="tutorial-install-and-use-a-net-core-local-tool-using-the-net-core-cli"></a>Esercitazione: Installare e usare uno strumento locale .NET Core usando l'interfaccia della riga di comando di .NET CoreTutorial: Install and use a .NET Core local tool using the .NET Core CLI

**Questo articolo si applica a:** ✔️ .NET Core 3.0 SDK e versioni successive

Questo tutorial ti insegna come installare e usare uno strumento locale. Si utilizza uno strumento creato nella [prima esercitazione di questa serie.](global-tools-how-to-create.md)

## <a name="prerequisites"></a>Prerequisites

* Completare la [prima esercitazione di questa serie.](global-tools-how-to-create.md)
* Installare il runtime di .NET Core 2.1.

  Per questa esercitazione si installa e si usa uno strumento destinato a .NET Core 2.1, pertanto è necessario che tale runtime sia installato nel computer. Per installare il runtime 2.1, vai alla pagina di download di [.NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1) e trova il collegamento di installazione di runtime nella colonna **Esegui app - Runtime.**

## <a name="create-a-manifest-file"></a>Creare un file manifestoCreate a manifest file

Per installare uno strumento solo per l'accesso locale (per la directory corrente e le sottodirectory), è necessario aggiungerlo a un file manifesto.

Dalla cartella *microsoft.botsay,* passare verso l'alto di un livello fino alla cartella del *repository:*

```console
cd ..
```

Creare un file manifesto eseguendo il comando [dotnet new:](dotnet-new.md)

```dotnetcli
dotnet new tool-manifest
```

L'output indica la corretta creazione del file.

```console
The template "Dotnet local tool manifest file" was created successfully.
```

Il file *.config/dotnet-tools.json* non contiene ancora strumenti:

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {}
}
```

Gli strumenti elencati in un file manifesto sono disponibili per la directory e le sottodirectory correnti. La directory corrente è quella che contiene la directory *.config* con il file manifesto.

Quando si utilizza un comando dell'interfaccia della riga di comando che fa riferimento a uno strumento locale, l'SDK cerca un file manifesto nella directory corrente e nelle directory padre. Se trova un file manifesto, ma il file non include lo strumento di riferimento, continua la ricerca verso l'alto nelle directory padre. La ricerca termina quando trova lo strumento di riferimento `isRoot` o `true`trova un file manifesto con impostato su .

## <a name="install-botsay-as-a-local-tool"></a>Installare botsay come strumento locale

Installare lo strumento dal pacchetto creato nella prima esercitazione:Install the tool from the package that you created in the first tutorial:

```dotnetcli
dotnet tool install --add-source ./microsoft.botsay/nupkg microsoft.botsay
```

Questo comando aggiunge lo strumento al file manifesto creato nel passaggio precedente. L'output del comando mostra in quale file manifesto si trova lo strumento appena installato:

 ```console
 You can invoke the tool from this directory using the following command:
 'dotnet tool run botsay' or 'dotnet botsay'
 Tool 'microsoft.botsay' (version '1.0.0') was successfully installed.
 Entry is added to the manifest file /home/name/repository/.config/dotnet-tools.json
 ```

Il file .config/dotnet-tools.json dispone ora di uno strumento:The *.config/dotnet-tools.json* file now has one tool:

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "microsoft.botsay": {
      "version": "1.0.0",
      "commands": [
        "botsay"
      ]
    }
  }
}
```

## <a name="use-the-tool"></a>Usare lo strumento

Richiamare lo strumento `dotnet tool run` eseguendo il comando dalla cartella del *repository:*

```dotnetcli
dotnet tool run botsay hello from the bot
```

## <a name="restore-a-local-tool-installed-by-others"></a>Ripristinare uno strumento locale installato da altri

In genere si installa uno strumento locale nella directory radice del repository. Dopo aver archiviato il file manifesto nel repository, altri sviluppatori possono ottenere il file manifesto più recente. Per installare tutti gli strumenti elencati nel file `dotnet tool restore` manifesto, è possibile eseguire un singolo comando.

1. Aprire il file *.config/dotnet-tools.json* e sostituire il contenuto con il seguente codice JSON:

   ```json
   {
     "version": 1,
     "isRoot": true,
     "tools": {
       "microsoft.botsay": {
         "version": "1.0.0",
         "commands": [
           "botsay"
         ]
       },
       "dotnetsay": {
         "version": "2.1.3",
         "commands": [
           "dotnetsay"
         ]
       }
     }
   }
   ```

1. Sostituire `<name>` con il nome utilizzato per creare il progetto.

1. Salvare le modifiche.

   Apportare questa modifica equivale a ottenere la versione più recente `dotnetsay` dal repository dopo che un altro utente ha installato il pacchetto per la directory del progetto.

1. Eseguire il comando `dotnet tool restore`.

   ```dotnetcli
   dotnet tool restore
   ```

   Il comando produce output simile all'esempio seguente:The command produces output like the following example:

   ```console
   Tool 'microsoft.botsay' (version '1.0.0') was restored. Available commands: botsay
   Tool 'dotnetsay' (version '2.1.3') was restored. Available commands: dotnetsay
   Restore was successful.
   ```

1. Verificare che gli strumenti siano disponibili:

   ```dotnetcli
   dotnet tool list
   ```

   L'output è un elenco di pacchetti e comandi, simile all'esempio seguente:The output is a list of packages and commands, similar to the following example:

   ```console
   Package Id      Version      Commands       Manifest
   --------------------------------------------------------------------------------------------
   microsoft.botsay 1.0.0        botsay         /home/name/repository/.config/dotnet-tools.json
   dotnetsay        2.1.3        dotnetsay      /home/name/repository/.config/dotnet-tools.json
   ```

1. Testare gli strumenti:

   ```dotnetcli
   dotnet tool run dotnetsay hello from dotnetsay
   dotnet tool run botsay hello from botsay
   ```

## <a name="update-a-local-tool"></a>Aggiornare uno strumento locale

La versione installata `dotnetsay` dello strumento locale è 2.1.3.  L'ultima versione è 2.1.4. Utilizzare il comando [dotnet tool update](dotnet-tool-update.md) per aggiornare lo strumento alla versione più recente.

```dotnetcli
dotnet tool update dotnetsay
```

L'output indica il nuovo numero di versione:

```console
Tool 'dotnetsay' was successfully updated from version '2.1.3' to version '2.1.4'
(manifest file /home/name/repository/.config/dotnet-tools.json).
```

Il comando update trova il primo file manifesto che contiene l'ID del pacchetto e lo aggiorna. Se tale ID pacchetto non è presente in alcun file manifesto incluso nell'ambito della ricerca, l'SDK aggiunge una nuova voce al file manifesto più vicino. L'ambito di ricerca si trova tramite le directory padre finché non viene trovato un file manifesto con. `isRoot = true`

## <a name="remove-local-tools"></a>Rimuovere gli strumenti locali

Rimuovere gli strumenti installati eseguendo il comando [dotnet tool uninstall:](dotnet-tool-uninstall.md)

```dotnetcli
dotnet tool uninstall microsoft.botsay
```

```dotnetcli
dotnet tool uninstall dotnetsay
```

## <a name="troubleshoot"></a>Risolvere problemi

Se viene visualizzato un messaggio di errore durante l'esercitazione, vedere Risolvere i problemi di [utilizzo degli strumenti .NET Core](troubleshoot-usage-issues.md).

## <a name="see-also"></a>Vedere anche

Per altre informazioni, vedere [Strumenti di .NET CoreFor](global-tools.md) more information, see .NET Core tools
