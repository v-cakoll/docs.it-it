---
ms.openlocfilehash: 5d5423d18091545ad9d50325900f5a9a4fff6dd9
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622014"
---
### <a name="fixed-a-hang-when-listbox-contains-duplicate-value-types"></a>Risoluzione di un'interruzione quando Listbox contiene tipi di valore duplicati

#### <a name="details"></a>Dettagli

È stato risolto un problema per cui la virtualizzazione di una classe <xref:System.Windows.Controls.ItemsControl> può interrompersi durante lo scorrimento quando la relativa raccolta Items contiene oggetti con tipi di valore duplicati.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Principale|
|Version|4.8|
|Type|Runtime|
