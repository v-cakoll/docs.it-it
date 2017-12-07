---
title: Installare .NET Framework 3.5 in Windows 10, Windows 8.1 e Windows 8
description: Informazioni sull'installazione di .NET Framework 3.5 in Windows 10, Windows 8.1 e Windows 8.
author: rlander
ms.author: mairaw
ms.date: 11/27/2017
ms.topic: article
ms.prod: .net-framework
ms.openlocfilehash: 51c412733b76777a78c4a739ce9b077acc86f069
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2017
---
# <a name="install-the-net-framework-35-on-windows-10-windows-81-and-windows-8"></a>Installare .NET Framework 3.5 in Windows 10, Windows 8.1 e Windows 8

Può essere necessario avere .NET Framework 3.5 installato per eseguire determinate app in Windows 10, Windows 8.1 e Windows 8. e si applicano anche alle versioni precedenti di Windows.

## <a name="install-the-net-framework-35-on-demand"></a>Installare .NET Framework 3.5 su richiesta

Se si prova a eseguire un'app che richiede .NET Framework 3.5 può essere visualizzata la finestra di dialogo di configurazione seguente. Scegliere **Installa la funzionalità** per abilitare .NET Framework 3.5. Per questa opzione è necessaria una connessione Internet.

![Finestra di dialogo di installazione di .NET Framework](./media/dotnet-framework-installation-dialog.jpg)

## <a name="enable-the-net-framework-35-in-control-panel"></a>Abilitare .NET Framework 3.5 dal Pannello di controllo

.NET Framework 3.5 può essere abilitato dal Pannello di controllo di Windows. Per questa opzione è necessaria una connessione Internet.

1. Premere il tasto Windows ![Logo Windows](https://i-msdn.sec.s-msft.com/dynimg/IC721376.jpeg) sulla tastiera, digitare "Funzionalità Windows" e premere INVIO. Viene visualizzata la finestra di dialogo **Attivazione o disattivazione delle funzionalità Windows**.

2. Selezionare la casella di controllo **.NET Framework 3.5 (include .NET 2.0 e 3.0)**, selezionare **OK** e riavviare il computer, se richiesto.

   ![Installazione di .NET tramite il Pannello di controllo](./media/dotnet-control-panel.png)

   Non è necessario selezionare gli elementi figlio per l'**attivazione HTTP di Windows Communication Foundation (WCF)** e per l'**attivazione non HTTP di Windows Communication Foundation (WCF)**, a meno che, in qualità di sviluppatore o amministratore del server, non si richieda questa funzionalità.

## <a name="troubleshoot-the-installation-of-the-net-framework-35"></a>Risolvere i problemi relativi all'installazione di .NET Framework 3.5

Durante l'installazione può verificarsi un errore 0x800f0906, 0x800f0907, 0x800f081f o 0x800F0922. In tal caso, vedere [Errore di installazione di .NET Framework 3.5: 0x800f0906, 0x800f0907 o 0x800f081f](https://support.microsoft.com/help/2734782/net-framework-3-5-installation-error-0x800f0906--0x800f081f--0x800f09) per informazioni su come risolvere questi problemi.

Se uno dei metodi illustrati nell'articolo precedente non riesce o non è presente una connessione Internet, è necessario usare il supporto di installazione di Windows. Per altre informazioni, vedere [Deploy .NET Framework 3.5 by using Deployment Image Servicing and Management (DISM)](https://technet.microsoft.com/library/Dn482069.aspx) (Distribuire .NET Framework 3.5 usando Gestione e manutenzione immagini distribuzione). Se il supporto di installazione non è disponibile, vedere [Creare supporti di installazione per Windows](https://support.microsoft.com/help/15088/windows-create-installation-media).