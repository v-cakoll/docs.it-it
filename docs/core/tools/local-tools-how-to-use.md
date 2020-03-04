---
title: 'Esercitazione: installare e usare gli strumenti locali di .NET Core'
description: Informazioni su come installare e usare uno strumento .NET come strumento locale.
ms.date: 02/12/2020
ms.openlocfilehash: a4355886513040e2436bdbd87905e5baee2dd7a5
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156699"
---
# <a name="tutorial-install-and-use-a-net-core-local-tool-using-the-net-core-cli"></a>Esercitazione: installare e usare uno strumento locale di .NET Core usando il interfaccia della riga di comando di .NET Core

**Questo articolo si applica a:** ✔️ .net core 3,0 SDK e versioni successive

Questa esercitazione illustra come installare e usare uno strumento locale. Usare uno strumento creato nella [prima esercitazione di questa serie](global-tools-how-to-create.md).

## <a name="prerequisites"></a>Prerequisites

* Completare la [prima esercitazione di questa serie](global-tools-how-to-create.md).
* Installare il runtime di .NET Core 2,1.

  Per questa esercitazione si installa e si usa uno strumento destinato a .NET Core 2,1, quindi è necessario che il Runtime sia installato nel computer. Per installare il runtime di 2,1, passare alla [pagina di download di .NET Core 2,1](https://dotnet.microsoft.com/download/dotnet-core/2.1) e trovare il collegamento di installazione di runtime nella colonna **Run Apps-Runtime** .

## <a name="create-a-manifest-file"></a>Creazione di un file manifesto

Per installare uno strumento solo per l'accesso locale (per la directory e le sottodirectory correnti), è necessario aggiungerlo a un file manifesto.

Dalla cartella *Microsoft. botsay* passare a un livello superiore nella cartella del *repository* :

```console
cd ..
```

Creare un file manifesto eseguendo il comando [DotNet New](dotnet-new.md) :

```dotnetcli
dotnet new tool-manifest
```

L'output indica che la creazione del file è riuscita.

```console
The template "Dotnet local tool manifest file" was created successfully.
```

Il file *. config/DotNet-Tools. JSON* non contiene ancora strumenti:

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {}
}
```

Gli strumenti elencati in un file manifesto sono disponibili per la directory e le sottodirectory correnti. La directory corrente è quella che contiene la directory *. config* con il file manifesto.

Quando si usa un comando CLI che fa riferimento a uno strumento locale, l'SDK Cerca un file manifesto nella directory corrente e nelle directory padre. Se trova un file manifesto, ma il file non include lo strumento a cui si fa riferimento, continua la ricerca nelle directory padre. La ricerca termina quando trova lo strumento a cui si fa riferimento o trova un file manifesto con `isRoot` impostato su `true`.

## <a name="install-botsay-as-a-local-tool"></a>Installare botsay come strumento locale

Installare lo strumento dal pacchetto creato nella prima esercitazione:

```dotnetcli
dotnet tool install --add-source ./microsoft.botsay/nupkg microsoft.botsay
```

Questo comando aggiunge lo strumento al file manifesto creato nel passaggio precedente. L'output del comando Mostra il file manifesto in cui si trova lo strumento appena installato:

 ```console
 You can invoke the tool from this directory using the following command:
 'dotnet tool run botsay' or 'dotnet botsay'
 Tool 'microsoft.botsay' (version '1.0.0') was successfully installed.
 Entry is added to the manifest file /home/name/repository/.config/dotnet-tools.json
 ```

Il file *. config/DotNet-Tools. JSON* dispone ora di uno strumento:

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

Richiamare lo strumento eseguendo il comando `dotnet tool run` dalla cartella *repository* :

```dotnetcli
dotnet tool run botsay hello from the bot
```

## <a name="restore-a-local-tool-installed-by-others"></a>Ripristinare uno strumento locale installato da altri utenti

Viene in genere installato uno strumento locale nella directory radice del repository. Dopo l'archiviazione del file manifesto nel repository, altri sviluppatori possono ottenere il file manifesto più recente. Per installare tutti gli strumenti elencati nel file manifesto, è possibile eseguire un singolo comando `dotnet tool restore`.

1. Aprire il file *config/DotNet-Tools. JSON* e sostituire il contenuto con il codice JSON seguente:

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

1. Sostituire `<name>` con il nome usato per creare il progetto.

1. Salvare le modifiche.

   Per apportare questa modifica, è possibile ottenere la versione più recente dal repository dopo che un altro utente ha installato il pacchetto `dotnetsay` per la directory del progetto.

1. Eseguire il comando `dotnet tool restore`.

   ```dotnetcli
   dotnet tool restore
   ```

   Il comando genera un output simile all'esempio seguente:

   ```console
   Tool 'microsoft.botsay' (version '1.0.0') was restored. Available commands: botsay
   Tool 'dotnetsay' (version '2.1.3') was restored. Available commands: dotnetsay
   Restore was successful.
   ```

1. Verificare che gli strumenti siano disponibili:

   ```dotnetcli
   dotnet tool list
   ```

   L'output è un elenco di pacchetti e comandi, in modo simile all'esempio seguente:

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

La versione installata dello strumento locale `dotnetsay` è 2.1.3.  La versione più recente è 2.1.4. Usare il comando [DotNet Tool Update](dotnet-tool-update.md) per aggiornare lo strumento alla versione più recente.

```dotnetcli
dotnet tool update dotnetsay
```

L'output indica il nuovo numero di versione:

```console
Tool 'dotnetsay' was successfully updated from version '2.1.3' to version '2.1.4'
(manifest file /home/name/repository/.config/dotnet-tools.json).
```

Il comando Update trova il primo file manifesto che contiene l'ID del pacchetto e lo aggiorna. Se non è presente alcun ID pacchetto in un file manifesto nell'ambito della ricerca, l'SDK aggiunge una nuova voce al file manifesto più vicino. L'ambito di ricerca è attivo attraverso le directory padre fino a quando non viene trovato un file manifesto con `isRoot = true`.

## <a name="remove-local-tools"></a>Rimuovi strumenti locali

Rimuovere gli strumenti installati eseguendo il comando [DotNet Tool uninstall](dotnet-tool-uninstall.md) :

```dotnetcli
dotnet tool uninstall microsoft.botsay
```

```dotnetcli
dotnet tool uninstall dotnetsay
```

## <a name="troubleshoot"></a>Risolvere problemi

Se viene visualizzato un messaggio di errore mentre si segue l'esercitazione, vedere [risolvere i problemi di utilizzo degli strumenti .NET Core](troubleshoot-usage-issues.md).

## <a name="see-also"></a>Vedere anche

Per altre informazioni, vedere [strumenti di .NET Core](global-tools.md)
