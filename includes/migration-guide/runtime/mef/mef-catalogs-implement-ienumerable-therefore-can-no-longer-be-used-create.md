---
ms.openlocfilehash: 598df2121b480d411dac9c5571772a4a8d22b5ff
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620341"
---
### <a name="mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a>I cataloghi MEF implementano IEnumerable e quindi non è più possibile usarli per creare un serializzatore

#### <a name="details"></a>Dettagli

A partire da .NET Framework 4.5, i cataloghi MEF implementano IEnumerable e quindi non è più possibile usarli per creare un serializzatore (oggetto <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName>). Il tentativo di serializzare un catalogo MEF genera un'eccezione.

#### <a name="suggestion"></a>Suggerimento

Non è più possibile usare MEF per creare un serializzatore

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Principale|
|Version|4.5|
|Type|Runtime|
