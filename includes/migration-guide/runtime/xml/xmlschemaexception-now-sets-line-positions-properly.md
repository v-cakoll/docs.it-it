---
ms.openlocfilehash: c3e39e49747be709977d7fba3c39b59f5575c40d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620506"
---
### <a name="xmlschemaexception-now-sets-line-positions-properly"></a>XmlSchemaException ora imposta correttamente le posizioni delle righe

#### <a name="details"></a>Dettagli

Se il valore <xref:System.Xml.Linq.LoadOptions.SetLineInfo> viene passato al metodo Load e si verifica un errore di convalida, le proprietà <xref:System.Xml.Schema.XmlSchemaException.LineNumber> e <xref:System.Xml.Schema.XmlSchemaException.LinePosition> contengono ora informazioni sulla riga.

#### <a name="suggestion"></a>Suggerimento

È necessario aggiornare il codice di gestione delle eccezioni che presuppone che le proprietà <xref:System.Xml.Schema.XmlSchemaException.LineNumber> e <xref:System.Xml.Schema.XmlSchemaException.LinePosition> non vengano impostate, perché queste proprietà vengono ora impostate correttamente quando il metodo SetLineInfo viene usato durante il caricamento di XML.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Xml.Linq.LoadOptions.SetLineInfo?displayProperty=nameWithType></li></ul>|
