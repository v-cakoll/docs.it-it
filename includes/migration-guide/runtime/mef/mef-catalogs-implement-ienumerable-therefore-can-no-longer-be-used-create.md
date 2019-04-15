---
ms.openlocfilehash: 4cc91e7c6054fdb8e96cecf7120df5b9f25de56c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235573"
---
### <a name="mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a>I cataloghi MEF implementano IEnumerable e quindi non è più possibile usarli per creare un serializzatore

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.5, i cataloghi MEF implementano IEnumerable e quindi non è più possibile usarli per creare un serializzatore (oggetto <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name>). Il tentativo di serializzare un catalogo MEF genera un'eccezione.|
|Suggerimento|Non è più possibile usare MEF per creare un serializzatore|
|Ambito|Principale|
|Versione|4.5|
|Tipo|Runtime|
