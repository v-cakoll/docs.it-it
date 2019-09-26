---
title: Come installare il generatore di modelli
description: Informazioni su come installare lo strumento del generatore di modelli di ML.NET
author: luisquintanilla
ms.author: luquinta
ms.date: 06/21/2019
ms.custom: mvc, how-to
ms.openlocfilehash: b0d45ab7807bf84b98c58e85580d5aa04d0c5f7d
ms.sourcegitcommit: 1e72e2990220b3635cebc39586828af9deb72d8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2019
ms.locfileid: "71306319"
---
# <a name="how-to-install-mlnet-model-builder"></a>Come installare il generatore di modelli di ML.NET

Di seguito viene descritto come installare il generatore di modelli di ML.NET per aggiungere il Machine Learning alle applicazioni .NET.

> [!NOTE]
> Il generatore di modelli è attualmente in anteprima.

## <a name="pre-requisites"></a>Prerequisiti

- Visual Studio 2017 15.9.12 o versione successiva/Visual Studio 2019
- SDK .NET Core 2.1 o versione successiva

## <a name="limitations"></a>Limitazioni

- L'estensione del generatore di modelli di ML.NET attualmente funziona solo in Visual Studio in Windows.
- Limite del set di dati di training di 1 GB
- SQL Server ha un limite di 100 migliaia di righe per il training
- Microsoft SQL Server Data Tools per Visual Studio 2017 non è supportato

## <a name="install"></a>Installazione

Il generatore di modelli di ML.NET può essere installato tramite Visual Studio Marketplace o dall'interno di Visual Studio. 

### <a name="visual-studio-marketplace"></a>Visual Studio Marketplace

1. Scaricare da [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07)
1. Seguire i messaggi visualizzati per eseguire l'installazione nella versione di Visual Studio in uso

### <a name="visual-studio-2017"></a>Visual Studio 2017

1. Nella barra dei menu selezionare **Strumenti** > **Estensioni e aggiornamenti**

    ![Finestra di dialogo VS2017 Open Extensions Manager](./media/install-model-builder/vs2017-open-extensions-manager.png)

1. All'interno del prompt *Estensioni e aggiornamenti* selezionare il nodo *Online*.
1. Nella barra di ricerca cercare *ML.NET Model Builder* e selezionare ML.NET Model Builder (Preview) dai risultati

    ![VS2017 cercare e installare l'estensione del generatore di modelli nella finestra di dialogo Gestione estensioni](./media/install-model-builder/vs2017-install-model-builder.png)

1. Seguire i messaggi visualizzati per completare l'installazione

### <a name="visual-studio-2019"></a>Visual Studio 2019

1. Nella barra dei menu selezionare **Estensioni** > **Gestisci estensioni**

    ![Finestra di dialogo VS2019 Open Extensions Manager](./media/install-model-builder/vs2019-open-extensions-manager.png)

1. All'interno del prompt *Estensioni e aggiornamenti* selezionare il nodo *Online*.
1. Digitare *ML.NET Model Builder* nella barra di ricerca e selezionare ML.NET Model Builder (Preview)

    ![VS2019 cercare e installare l'estensione del generatore di modelli nella finestra di dialogo Gestione estensioni](./media/install-model-builder/vs2019-install-model-builder.png)

1. Seguire i messaggi visualizzati per completare l'installazione

## <a name="uninstall"></a>Disinstallare

### <a name="visual-studio-2017"></a>Visual Studio 2017

1. Nella barra dei menu selezionare **Strumenti** > **Estensioni e aggiornamenti**

    ![Finestra di dialogo Apri Gestione estensioni di VS2017](./media/install-model-builder/vs2017-open-extensions-manager.png)

1. All'interno del prompt *Estensioni e aggiornamenti* espandere il nodo *Installati* e selezionare *Strumenti*
1. Selezionare ML.NET Model Builder (Preview) dall'elenco degli strumenti e quindi selezionare *Disinstalla*

    ![VS2017 ricerca e Disinstalla estensione del generatore di modelli nella finestra di dialogo Gestione estensioni](./media/install-model-builder/vs2017-uninstall-model-builder.png)

1. Seguire i messaggi visualizzati per completare la disinstallazione.

### <a name="visual-studio-2019"></a>Visual Studio 2019

1. Nella barra dei menu selezionare **Estensioni** > **Gestisci estensioni**

    ![Finestra di dialogo Apri Gestione estensioni di VS2019](./media/install-model-builder/vs2019-open-extensions-manager.png)

1. All'interno del prompt *Estensioni e aggiornamenti* espandere il nodo *Installati* e selezionare *Strumenti*
1. Selezionare ML.NET Model Builder (Preview) dall'elenco degli strumenti e quindi selezionare *Disinstalla*

    ![VS2019 ricerca e Disinstalla estensione del generatore di modelli nella finestra di dialogo Gestione estensioni](./media/install-model-builder/vs2019-uninstall-model-builder.png)

1. Seguire i messaggi visualizzati per completare la disinstallazione.

## <a name="upgrade"></a>Aggiornamento

Il processo di aggiornamento è simile al processo di installazione. Scaricare la versione più recente da Visual Studio Marketplace o usare Gestione estensioni in Visual Studio.
