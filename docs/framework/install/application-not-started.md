---
title: Risoluzione dei problemi 'Impossibile riavviare l'applicazione'
description: Informazioni su come eseguire se viene visualizzata la finestra di dialogo "Impossibile iniziare l'applicazione".
ms.date: 09/05/2019
ms.openlocfilehash: 864c6ea23e9a048f060eee39d904bd4377be5084
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "76965906"
---
# <a name="troubleshooting-a-this-application-could-not-be-started-error-message"></a>Risoluzione dei problemi relativi a un messaggio di errore "Impossibile utilizzare l'applicazione"

Le applicazioni sviluppate per .NET Framework richiedono in genere l'installazione di una versione specifica di .NET Framework nel sistema. In alcuni casi, è possibile tentare di eseguire un'applicazione senza una versione installata o la versione prevista di .NET Framework presente. Questo spesso produce una finestra di dialogo di errore simile al seguente:

![Impossibile avviare l'applicazione](media/application-not-started/app-could-not-be-started.png)

Ciò indica in genere una delle seguenti condizioni:

- Un'installazione di .NET Framework nel sistema è danneggiata.

- La versione di .NET Framework necessaria per l'applicazione non può essere rilevata.

Per risolvere questo problema in modo da poter eseguire l'applicazione, eseguire le operazioni seguenti:

1. Scaricare lo strumento di ripristino di [.NET Framework (NetFxRepairTool.exe)](https://www.microsoft.com/download/details.aspx?id=30135). Lo strumento viene eseguito automaticamente al termine del download.

1. Se lo strumento di ripristino di .NET Framework consiglia un'azione aggiuntiva, ad esempio quelle illustrate nella figura seguente, selezionare **Avanti**.

   ![Modifiche consigliate](media/application-not-started/repair-tool-recommended-changes.png)

1. Gli strumenti di ripristino di .NET Framework visualizzano una finestra di dialogo illustrata nella figura seguente per indicare che le modifiche sono state completate. Lasciare aperta la finestra di dialogo mentre si tenta di eseguire nuovamente l'applicazione. Questa operazione dovrebbe avere esito positivo se lo strumento di ripristino di .NET Framework ha identificato e corretto un'installazione danneggiata di .NET Framework.

   ![Modifiche consigliate](media/application-not-started/repair-tool-changes-complete.png)

1. Se l'applicazione viene eseguita correttamente, selezionare il pulsante **Fine.** In caso contrario, selezionare il pulsante **Avanti.**

1. Se è stato selezionato il pulsante **Avanti,** lo strumento di ripristino di .NET Framework visualizza una finestra di dialogo simile alla seguente. Selezionare il pulsante Fine per inviare informazioni diagnostiche a Microsoft.Select the **Finish** button to send diagnostic information to Microsoft.

   ![Impossibile risolvere il problema](media/application-not-started/repair-tool-no-resolution.png)

1. Se non è ancora possibile eseguire l'applicazione, installare la versione più recente di .NET Framework supportata dalla versione di Windows in uso, come illustrato nella tabella seguente.

   |Versione di Windows|Installazione di .NET Framework|
   |---|---|
   |Aggiornamento dell'anniversario di Windows 10 e versioni successive|[Runtime di .NET Framework 4.8](https://dotnet.microsoft.com/download/dotnet-framework/net48)|
   |Windows 10, Windows 10 Novembre Aggiornamento|[.NET Framework 4.6.2](https://dotnet.microsoft.com/download/dotnet-framework/net462)|
   |Windows 8.1|[Runtime di .NET Framework 4.8](https://dotnet.microsoft.com/download/dotnet-framework/net48)|
   |Windows 8|[.NET Framework 4.6.1](https://dotnet.microsoft.com/download/dotnet-framework/net461)|
   |Windows 7 SP1|[Runtime di .NET Framework 4.8](https://dotnet.microsoft.com/download/dotnet-framework/net48)|
   |Windows Vista SP2|[.NET Framework 4.6](https://dotnet.microsoft.com/download/dotnet-framework/net46)|

   > [!NOTE]
   > .NET Framework 4.8 è preinstallato su Windows 10 maggio 2019 aggiornamento.

1. Tentare di avviare l'applicazione.

1. In alcuni casi, è possibile che venga visualizzata una finestra di dialogo simile alla seguente, che richiede di installare .NET Framework 3.5. Selezionare **Scarica e installa questa funzionalità** per installare .NET Framework 3.5, quindi avviare nuovamente l'applicazione.

   ![Impossibile risolvere il problema](media/application-not-started/install-3-5.png)

## <a name="see-also"></a>Vedere anche

- [Requisiti di sistema di .NET Framework](../get-started/system-requirements.md)
- [Guida all'installazione di .NET Framework](index.md)
- [Risolvere i problemi relativi alle installazioni e alle disinstallazioni bloccate di .NET Framework](troubleshoot-blocked-installations-and-uninstallations.md)
