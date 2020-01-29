---
title: Installare i file IntelliSense localizzati
description: Informazioni su come configurare il computer di sviluppo per l'uso di file IntelliSense localizzati per i progetti .NET Core in Visual Studio.
ms.date: 01/23/2020
ms.openlocfilehash: 58b462507edf953a6c28aadbb9e3239a5cbe05b2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733645"
---
# <a name="how-to-install-localized-intellisense-files-for-net-core"></a>Come installare i file IntelliSense localizzati per .NET Core

[IntelliSense](/visualstudio/ide/using-intellisense) è un supporto per il completamento del codice disponibile in diversi ambienti di sviluppo integrato (IDE), ad esempio Visual Studio. Per impostazione predefinita, quando si sviluppano progetti .NET Core, l'SDK include solo la versione in lingua inglese dei file IntelliSense. In questo articolo viene descritto quanto segue:

- Come installare la versione localizzata di questi file.
- Come modificare l'installazione di Visual Studio per usare una lingua diversa.

## <a name="prerequisites"></a>Prerequisiti

- [.NET Core 3.0 SDK](https://dotnet.microsoft.com/download/dotnet-core) o versione successiva.
- [Visual Studio 2019 versione 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o successiva.

## <a name="download-and-install-the-localized-intellisense-files"></a>Scaricare e installare i file IntelliSense localizzati

> [!IMPORTANT]
> Per questa procedura è necessario avere le autorizzazioni di amministratore per copiare i file IntelliSense nella cartella di installazione di .NET Core.

1. Passare alla pagina per il [download dei file IntelliSense](https://dotnet.microsoft.com/download/dotnet-core/intellisense).

1. Scaricare il file IntelliSense per la lingua e la versione che si vuole usare.

1. Estrarre il contenuto del file ZIP.

1. Passare alla cartella IntelliSense di .NET Core.

   1. Passare alla cartella di installazione di .NET Core. Per impostazione predefinita, è in *%ProgramFiles%\dotnet\packs*.
   1. Scegliere l'SDK per cui si vuole installare IntelliSense e passare al percorso associato. Sono disponibili le seguenti opzioni:

      | Tipo di SDK        | Percorso                               |
      | --------------- | ---------------------------------- |
      | .NET Core       | *Microsoft.NETCore.App.Ref*        |
      | Windows Desktop | *Microsoft.WindowsDesktop.App.Ref* |
      | .NET Standard   | *NETStandard.Library.Ref*          |
   
   1. Passare alla versione per cui si vuole installare la versione localizzata di IntelliSense. Ad esempio, *3.1.0*.
   1. Aprire la cartella *ref*.
   1. Aprire la cartella del moniker. Ad esempio, *netcoreapp3.1*.

   Il percorso completo a cui si accede dovrebbe essere quindi simile a *C:\Programmi\dotnet\packs\Microsoft.NETCore.App.Ref\3.1.0\ref\netcoreapp3.1*.

1. Creare una sottocartella all'interno della cartella del moniker appena aperta. Il nome della cartella indica la lingua da usare. Nella tabella seguente vengono specificate le diverse opzioni:

   | Lingua:              | Nome cartella |
   | --------------------- | ----------- |
   | Portoghese brasiliano  | *pt-br*     |
   | Cinese (semplificato)  | *zh-hans*   |
   | Cinese (tradizionale) | *zh-hant*   |
   | Francese                | *fr*        |
   | Tedesco                | *de*        |
   | Italiano               | *it*        |
   | Giapponese              | *ja*        |
   | Coreano                | *ko*        |
   | Russo               | *ru*        |
   | Spagnolo               | *es*        |

1. Copiare i file con estensione *xml* estratti nel passaggio 3 in questa nuova cartella. I file con estensione *xml* sono suddivisi in base alle cartelle degli SDK, quindi copiarli nell'SDK corrispondente scelto nel passaggio 4.

## <a name="modify-visual-studio-language"></a>Modificare la lingua di Visual Studio

Per fare in modo che Visual Studio usi una lingua diversa per IntelliSense, installare il language pack appropriato. Questa operazione può essere eseguita [durante l'installazione](/visualstudio/install/install-visual-studio#step-6---install-language-packs-optional) o in un secondo momento modificando l'installazione di Visual Studio. Se Visual Studio è già configurato per la lingua scelta, l'installazione di IntelliSense è pronta.

### <a name="install-the-language-pack"></a>Installare il language pack

Se il language pack desiderato non è stato installato durante l'installazione, aggiornare Visual Studio come indicato di seguito per installare il language pack:

> [!IMPORTANT]
> Per installare, aggiornare o modificare Visual Studio, è necessario accedere con un account con autorizzazioni di amministratore. Per altre informazioni, vedere [Autorizzazioni utente e Visual Studio](/visualstudio/ide/user-permissions-and-visual-studio).

1. Individuare il programma di installazione di Visual Studio all'interno del computer in uso.

   Ad esempio, in un computer che esegue Windows 10 selezionare **Start** e scorrere fino alla lettera **P** in cui viene visualizzato come **Programma di installazione di Visual Studio**.

   ![Aprire il programma di installazione di Visual Studio da Windows](./media/localized-intellisense/vs-installer-windows-start.png)

   > [!NOTE]
   > È anche possibile trovare il programma di installazione di Visual Studio nella posizione seguente:
   >
   > `C:\Program Files (x86)\Microsoft Visual Studio\Installer\vs_installer.exe`

   Prima di continuare, potrebbe essere necessario aggiornare il programma di installazione. In questo caso, seguire i prompt.

1. Nel programma di installazione cercare l'edizione di Visual Studio a cui si vuole aggiungere il language pack e quindi scegliere **Modifica**.

   ![Aggiornare o modificare Visual Studio](./media/localized-intellisense/vs-installer-modify.png)

   > [!IMPORTANT]
   > Se non viene visualizzato il pulsante **Modifica** ma viene invece visualizzato il pulsante **Aggiorna**, è necessario aggiornare Visual Studio prima di poter modificare l'installazione.
   > Al termine dell'aggiornamento, verrà visualizzato il pulsante **Modifica**.

1. Nella scheda **Language pack** selezionare o deselezionare le lingue da installare o disinstallare.

   ![Scheda Language pack di Visual Studio](./media/localized-intellisense/vs-modify-language-packs.png)

1. Scegliere **Modifica**. L'aggiornamento viene avviato.

### <a name="modify-language-settings-in-visual-studio"></a>Modificare le impostazioni di lingua in Visual Studio

Dopo aver installato i language pack desiderati, modificare le impostazioni di Visual Studio per usare una lingua diversa:

1. Apri Visual Studio.

1. Nella finestra iniziale scegliere **Continua senza codice**.

1. Nella barra dei menu selezionare **strumenti** > **Opzioni**. Verrà visualizzata la finestra di dialogo Opzioni.

1. Nel nodo **ambiente** scegliere **impostazioni internazionali**.

1. Nell'elenco a discesa **Lingua** selezionare la lingua desiderata. Scegliere **OK**. 

1. Una finestra di dialogo informa che è necessario riavviare Visual Studio per rendere effettive le modifiche. Scegliere **OK**.

1. Riavviare Visual Studio.

Al termine di questa operazione, IntelliSense dovrebbe funzionare come previsto quando si apre un progetto .NET Core destinato alla versione dei file IntelliSense appena installati.

## <a name="see-also"></a>Vedere anche

- [IntelliSense in Visual Studio](/visualstudio/ide/using-intellisense)
