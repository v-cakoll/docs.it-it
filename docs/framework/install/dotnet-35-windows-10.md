---
title: Installare .NET Framework 3.5 in Windows 10, Windows 8.1 e Windows 8
description: Informazioni sull'installazione di .NET Framework 3.5 in Windows 10, Windows 8.1 e Windows 8.
author: rlander
ms.author: mairaw
keywords: .NET Framework, Installare
ms.date: 05/26/2017
ms.topic: article
ms.prod: .net-framework
ms.technology: vs-ide-deployment
ms.devlang: dotnet
ms.assetid: 67cda1d5-c6g4-4eb5-93e6-4f478de07ff7
ms.translationtype: HT
ms.sourcegitcommit: 21c6a1485f3d0c38bde065d6ecc7b07d5e424c1d
ms.openlocfilehash: 85a3cada074714c24015d90c26d94551f4f411f2
ms.contentlocale: it-it
ms.lasthandoff: 08/05/2017

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

