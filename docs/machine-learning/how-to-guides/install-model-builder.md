---
title: Come installare il generatore di modelli
description: Informazioni su come installare lo strumento del generatore di modelli di ML.NET
author: luisquintanilla
ms.author: luquinta
ms.date: 06/21/2019
ms.custom: mvc, how-to
ms.openlocfilehash: 54ab595c56f816517180aab48022c7df207fe84d
ms.sourcegitcommit: 52e588dc2ee74d484cd07ac60076be25cbf777ab
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/27/2019
ms.locfileid: "67410569"
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

## <a name="install"></a>Installazione di

Il generatore di modelli di ML.NET può essere installato tramite Visual Studio Marketplace o dall'interno di Visual Studio. 

### <a name="visual-studio-marketplace"></a>Visual Studio Marketplace

1. Scaricare da [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07)
1. Seguire i messaggi visualizzati per eseguire l'installazione nella versione di Visual Studio in uso

### <a name="visual-studio-2017"></a>Visual Studio 2017

1. Nella barra dei menu selezionare **Strumenti** > **Estensioni e aggiornamenti**
1. All'interno del prompt *Estensioni e aggiornamenti* selezionare il nodo *Online*.
1. Nella barra di ricerca cercare *ML.NET Model Builder* e selezionare ML.NET Model Builder (Preview) dai risultati
1. Seguire i messaggi visualizzati per completare l'installazione

### <a name="visual-studio-2019"></a>Visual Studio 2019

1. Nella barra dei menu selezionare **Estensioni** > **Gestisci estensioni**
1. All'interno del prompt *Estensioni e aggiornamenti* selezionare il nodo *Online*.
1. Digitare *ML.NET Model Builder* nella barra di ricerca e selezionare ML.NET Model Builder (Preview)
1. Seguire i messaggi visualizzati per completare l'installazione

## <a name="uninstall"></a>Disinstalla

### <a name="visual-studio-2017"></a>Visual Studio 2017

1. Nella barra dei menu selezionare **Strumenti** > **Estensioni e aggiornamenti**
1. All'interno del prompt *Estensioni e aggiornamenti* espandere il nodo *Installati* e selezionare *Strumenti*
1. Selezionare ML.NET Model Builder (Preview) dall'elenco degli strumenti e quindi selezionare *Disinstalla*
1. Seguire i messaggi visualizzati per completare la disinstallazione.

### <a name="visual-studio-2019"></a>Visual Studio 2019

1. Nella barra dei menu selezionare **Estensioni** > **Gestisci estensioni**
1. All'interno del prompt *Estensioni e aggiornamenti* espandere il nodo *Installati* e selezionare *Strumenti*
1. Selezionare ML.NET Model Builder (Preview) dall'elenco degli strumenti e quindi selezionare *Disinstalla*
1. Seguire i messaggi visualizzati per completare la disinstallazione.

## <a name="upgrade"></a>Aggiornamento

Il processo di aggiornamento è simile al processo di installazione. Scaricare la versione più recente da Visual Studio Marketplace o usare Gestione estensioni in Visual Studio.
