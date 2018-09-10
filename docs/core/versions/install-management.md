---
title: Gestire le installazioni di .NET Core
description: Gestire più versioni di .NET Core SDK e .NET Core Runtime nel computer usando strategie di installazione side-by-side.
author: leecow
ms.author: wiwagn
ms.date: 08/22/2018
ms.openlocfilehash: 06c3f43e7917efb8fd31898044d8f5d920c2cada
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43485447"
---
# <a name="manage-net-core-installations"></a>Gestire le installazioni di .NET Core

.NET Core consente di installare più versioni di SDK e Runtime side-by-side, offrendo flessibilità di dipendenza dalle versioni per la compilazione e l'esecuzione di applicazioni .NET Core. Questo tipo di installazioni e il roll-forward automatico delle versioni offrono diversi vantaggi e uno svantaggio. Man mano che gli aggiornamenti di .NET Core SDK o .NET Core Runtime vengono installati, le versioni precedenti rimangono su disco. L'installazione di più versioni aumenta l'utilizzo del disco nel tempo. Sono stati rilasciati più di 50 aggiornamenti di .NET Core SDK. È possibile che nel sistema siano state installate numerose versioni di SDK e Runtime che è possibile rimuovere.

## <a name="safe-to-remove"></a>Rimozione sicura

La [selezione delle versioni di .NET Core](selection.md) e la compatibilità di runtime di .NET Core tra gli aggiornamenti consente la rimozione sicura delle versioni precedenti. Gli aggiornamenti al runtime di .NET Core sono compatibili all'interno delle versioni principali, ad esempio 1.x e 2.x. Inoltre, le nuove versioni di .NET Core SDK mantengono in genere la possibilità di creare applicazioni destinate a versioni precedenti del runtime in modo compatibile.

In generale, sono necessari solo l'SDK più recente e l'ultima versione patch dei runtime richiesti per l'applicazione. Le istanze in cui sono mantenute le versioni precedenti di SDK o Runtime includono le applicazioni basate su project.json.  Se l'applicazione non ha ragioni specifiche per mantenere le versioni precedenti di SDK o Runtime, è possibile rimuovere le versioni precedenti in modo sicuro.

I metodi per la rimozione di .NET Core variano a seconda della piattaforma e sono stati leggermente modificati da una versione di .NET Core all'altra. Per informazioni dettagliate sulla rimozione di versioni di .NET Core non più necessarie, vedere ['How to remove the .NET Core Runtime and SDK'](remove-runtime-sdk-versions.md) (Come rimuovere .NET Core Runtime e SDK) nella [documentazione di .NET Core](../index.md).
