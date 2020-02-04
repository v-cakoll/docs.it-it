---
title: Risoluzione dei problemi ' Impossibile avviare l'applicazione '
description: Informazioni sulle operazioni da eseguire se viene visualizzata la finestra di dialogo "Impossibile avviare l'applicazione".
ms.date: 09/05/2019
ms.openlocfilehash: 864c6ea23e9a048f060eee39d904bd4377be5084
ms.sourcegitcommit: feb42222f1430ca7b8115ae45e7a38fc4a1ba623
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/02/2020
ms.locfileid: "76965906"
---
# <a name="troubleshooting-a-this-application-could-not-be-started-error-message"></a>Risoluzione dei problemi relativi a un messaggio di errore "Impossibile avviare l'applicazione"

Per le applicazioni sviluppate per il .NET Framework in genere è necessario che nel sistema sia installata una versione specifica del .NET Framework. In alcuni casi, è possibile tentare di eseguire un'applicazione senza una versione installata o la versione prevista del .NET Framework presente. Questa operazione spesso genera una finestra di dialogo di errore simile alla seguente:

![Impossibile avviare l'applicazione](media/application-not-started/app-could-not-be-started.png)

Questo indica in genere una delle seguenti condizioni:

- Un .NET Framework installazione nel sistema è stato danneggiato.

- Non è possibile rilevare la versione del .NET Framework richiesta dall'applicazione.

Per risolvere questo problema in modo che sia possibile eseguire l'applicazione, eseguire le operazioni seguenti:

1. Scaricare lo [strumento di ripristino .NET Framework (NetFxRepairTool. exe)](https://www.microsoft.com/download/details.aspx?id=30135). Lo strumento viene eseguito automaticamente al termine del download.

1. Se lo strumento di ripristino .NET Framework consiglia di eseguire altre operazioni, ad esempio quelle illustrate nella figura seguente, fare clic su **Avanti**.

   ![Modifiche consigliate](media/application-not-started/repair-tool-recommended-changes.png)

1. Negli strumenti di ripristino .NET Framework viene visualizzata una finestra di dialogo illustrata nella figura seguente per indicare che le modifiche sono state completate. Lasciare aperta la finestra di dialogo mentre si tenta di eseguire di nuovo l'applicazione. Questa operazione dovrebbe avere esito positivo se lo strumento di ripristino .NET Framework ha identificato e corretto un'installazione .NET Framework danneggiata.

   ![Modifiche consigliate](media/application-not-started/repair-tool-changes-complete.png)

1. Se l'applicazione viene eseguita correttamente, selezionare il pulsante **fine** . In caso contrario, selezionare il pulsante **Avanti** .

1. Se è stato selezionato il pulsante **Avanti** , lo strumento .NET Framework Repair Visualizza una finestra di dialogo simile alla seguente. Selezionare il pulsante **fine** per inviare le informazioni di diagnostica a Microsoft.

   ![Non è possibile risolvere il problema](media/application-not-started/repair-tool-no-resolution.png)

1. Se non è ancora possibile eseguire l'applicazione, installare la versione più recente del .NET Framework supportata dalla versione di Windows, come illustrato nella tabella seguente.

   |Versione di Windows|Installazione .NET Framework|
   |---|---|
   |Aggiornamento dell'anniversario di Windows 10 e versioni successive|[Runtime di .NET Framework 4,8](https://dotnet.microsoft.com/download/dotnet-framework/net48)|
   |Windows 10, aggiornamento di novembre di Windows 10|[.NET Framework 4.6.2](https://dotnet.microsoft.com/download/dotnet-framework/net462)|
   |Windows 8.1|[Runtime di .NET Framework 4,8](https://dotnet.microsoft.com/download/dotnet-framework/net48)|
   |Windows 8|[.NET Framework 4.6.1](https://dotnet.microsoft.com/download/dotnet-framework/net461)|
   |Windows 7 SP1|[Runtime di .NET Framework 4,8](https://dotnet.microsoft.com/download/dotnet-framework/net48)|
   |Windows Vista SP2|[.NET Framework 4,6](https://dotnet.microsoft.com/download/dotnet-framework/net46)|

   > [!NOTE]
   > .NET Framework 4,8 è preinstallato in Windows 10 può essere aggiornato con il 2019.

1. Tentare di avviare l'applicazione.

1. In alcuni casi, è possibile che venga visualizzata una finestra di dialogo simile alla seguente, in cui viene chiesto di installare il .NET Framework 3,5. Selezionare **scaricare e installare questa funzionalità** per installare il .NET Framework 3,5, quindi avviare di nuovo l'applicazione.

   ![Non è possibile risolvere il problema](media/application-not-started/install-3-5.png)

## <a name="see-also"></a>Vedere anche

- [Requisiti di sistema .NET Framework](../get-started/system-requirements.md)
- [Guida all'installazione di .NET Framework](index.md)
- [Risolvere i problemi relativi alle installazioni e alle disinstallazioni bloccate di .NET Framework](troubleshoot-blocked-installations-and-uninstallations.md)
