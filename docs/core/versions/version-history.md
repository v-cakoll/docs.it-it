---
title: Cronologia delle versioni di .NET Core
description: Vedere la sequenza temporale per le versioni del runtime di .NET Core, di .NET Core SDK, del compilatore C# e del compilatore VB.NET.
ms.date: 07/26/2018
ms.openlocfilehash: 90fd4ba57620a3a005f2148c0335a76a6fa54a30
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2018
ms.locfileid: "42936639"
---
# <a name="net-core-version-history"></a>Cronologia delle versioni di NET Core

I numeri di versione per .NET Core sono complessi poiché .NET Core SDK e il Runtime di .NET Core vengono rilasciati con diverse cadenze. Le diverse cadenze indicano che il team è stato obbligato a eseguire solo due delle tre operazioni seguenti:

1. Eseguire rilasci indipendenti per consentire in particolar modo agli strumenti, C# e Visual Basic, di avanzare più rapidamente rispetto al Runtime di .NET Core.
2. Mantenere l'allineamento nei numeri di versione tra .NET Core SDK e il Runtime di .NET Core.
3. Usare il versionamento semantico per .NET Core SDK e il Runtime di .NET Core.

La versione 2.0.0 ha forzato l'allineamento di versione ed è proseguita in modo regolare per una versione. A dicembre 2017 è stata rilasciata una versione definitiva di .NET Core SDK senza una versione corrispondente del runtime di .NET Core. Il team ha scelto gli obiettivi 1 e 3, perdendo l'allineamento tra il Runtime di .NET Core e l'SDK. Diverse versioni di .NET Core SDK 2.1.x sono state rilasciate prima del Runtime di .NET Core 2.1. Poiché l'SDK non è compatibile in avanti, queste versioni SDK 2.1.x potrebbero non essere destinate al Runtime di .NET Core 2.1. Il team ha risposto alla notevole confusione passando agli obiettivi 1 e 2, tralasciando il versionamento semantico, come descritto in [Controllo delle versioni di .NET Core](index.md#versioning-details).

A causa della tempistica della decisione di tralasciare il versionamento semantico, sono state rilasciate delle versioni transitorie tra i numeri di versione 2.1.10x e 2.1.20x che anch'esse non possono essere destinate al Runtime di .NET Core 2.1.

Le prime due cifre dei numeri di versione vengono riallineati con la versione 2.1.0 del Runtime di .NET Core e la versione 2.1.300 di .NET Core SDK.

Informazioni dettagliate sulle versioni di singoli componenti, comprese le versioni del framework e del compilatore del linguaggio, sono disponibili nella [pagina di download di .NET Core](https://www.microsoft.com/net/download/dotnet-core/current). Per informazioni dettagliate sulle versioni precedenti, selezionare la versione richiesta nella [pagina degli archivi di download di .NET Core](https://www.microsoft.com/net/download/archives). Informazioni di supporto dettagliate sono disponibili nell'articolo che descrive i [criteri di supporto .NET](https://www.microsoft.com/net/Support/Policy) ufficiali.