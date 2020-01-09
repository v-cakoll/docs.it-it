---
title: Installare .NET Framework 3,5 in Windows 10, 8,1, 8
description: Informazioni sull'installazione di .NET Framework 3.5 in Windows 10, Windows 8.1 e Windows 8.
ms.date: 07/16/2018
ms.openlocfilehash: 208016e22eed324a3996552284072c6ad29637a5
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716384"
---
# <a name="install-the-net-framework-35-on-windows-10-windows-81-and-windows-8"></a>Installare .NET Framework 3.5 in Windows 10, Windows 8.1 e Windows 8

Può essere necessario avere .NET Framework 3.5 installato per eseguire determinate app in Windows 10, Windows 8.1 e Windows 8. e si applicano anche alle versioni precedenti di Windows.

## <a name="install-the-net-framework-35-on-demand"></a>Installare .NET Framework 3.5 su richiesta

Se si prova a eseguire un'app che richiede .NET Framework 3.5 può essere visualizzata la finestra di dialogo di configurazione seguente. Scegliere **Installa la funzionalità** per abilitare .NET Framework 3.5. Per questa opzione è necessaria una connessione Internet.

![Screenshot della finestra di dialogo di installazione di .NET Framework.](./media/dotnet-35-windows-10/dotnet-framework-installation-dialog.png)

### <a name="why-am-i-getting-this-pop-up"></a>Perché viene visualizzato questo popup?

.NET Framework è creato da Microsoft e offre un ambiente per l'esecuzione di applicazioni. Sono disponibili diverse versioni. Molte società sviluppano app da eseguire con .NET Framework e queste app sono destinate a una versione specifica. Se viene visualizzato questo popup, si sta tentando di eseguire un'applicazione che richiede .NET Framework versione 3.5, ma tale versione non è installata nel sistema in uso.

## <a name="enable-the-net-framework-35-in-control-panel"></a>Abilitare .NET Framework 3.5 dal Pannello di controllo

.NET Framework 3.5 può essere abilitato dal Pannello di controllo di Windows. Per questa opzione è necessaria una connessione Internet.

1. Premere il tasto Windows ![screenshot del logo della chiave di Windows.](./media/dotnet-35-windows-10/windows-keyboard-logo.png) sulla tastiera digitare "funzionalità Windows" e premere INVIO. Viene visualizzata la finestra di dialogo **Attivazione o disattivazione delle funzionalità Windows**.

2. Selezionare la casella di controllo **.NET Framework 3.5 (include .NET 2.0 e 3.0)** , selezionare **OK** e riavviare il computer, se richiesto.

   ![Screenshot che illustra l'installazione di .NET con il pannello di controllo.](./media/dotnet-35-windows-10/dotnet-control-panel.png)

   Non è necessario selezionare gli elementi figlio per l'**attivazione HTTP di Windows Communication Foundation (WCF)** e per l'**attivazione non HTTP di Windows Communication Foundation (WCF)** , a meno che, in qualità di sviluppatore o amministratore del server, non si richieda questa funzionalità.

## <a name="troubleshoot-the-installation-of-the-net-framework-35"></a>Risolvere i problemi relativi all'installazione di .NET Framework 3.5

Durante l'installazione può verificarsi un errore 0x800f0906, 0x800f0907, 0x800f081f o 0x800F0922. In tal caso, vedere [Errore di installazione di .NET Framework 3.5: 0x800f0906, 0x800f0907 o 0x800f081f](https://support.microsoft.com/help/2734782/net-framework-3-5-installation-error-0x800f0906--0x800f081f--0x800f09) per informazioni su come risolvere questi problemi.

Se il problema di installazione persiste o se non è disponibile una connessione a Internet, è possibile tentare l'installazione usando il supporto di installazione di Windows. Per altre informazioni, vedere [Deploy .NET Framework 3.5 by using Deployment Image Servicing and Management (DISM)](/windows-hardware/manufacture/desktop/deploy-net-framework-35-by-using-deployment-image-servicing-and-management--dism) (Distribuire .NET Framework 3.5 usando Gestione e manutenzione immagini distribuzione). Se il supporto di installazione non è disponibile, vedere [Creare supporti di installazione per Windows](https://support.microsoft.com/help/15088/windows-create-installation-media).

> [!WARNING]
> Se non intende usare Windows Update come origine per l'installazione di .NET Framework 3.5, è necessario usare esclusivamente le origini della stessa versione del sistema operativo di Windows corrispondente. L'uso un percorso di origine non corrisponde alla stessa versione di Windows non impedisce di installare una versione non corrispondente di .NET Framework 3.5. Tuttavia, in questo modo il sistema sarà in uno stato non supportato e inutilizzabile.
