---
ms.openlocfilehash: a5b3e325c13d2f56532ebc6ebb5c259d565a4952
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235724"
---
### <a name="xmlschemaexception-now-sets-line-positions-properly"></a>XmlSchemaException ora imposta correttamente le posizioni delle righe

|   |   |
|---|---|
|Dettagli|Se il valore <xref:System.Xml.Linq.LoadOptions.SetLineInfo> viene passato al metodo Load e si verifica un errore di convalida, le proprietà <xref:System.Xml.Schema.XmlSchemaException.LineNumber> e <xref:System.Xml.Schema.XmlSchemaException.LinePosition> contengono ora informazioni sulla riga.|
|Suggerimento|È necessario aggiornare il codice di gestione delle eccezioni che presuppone che le proprietà <xref:System.Xml.Schema.XmlSchemaException.LineNumber> e <xref:System.Xml.Schema.XmlSchemaException.LinePosition> non vengano impostate, perché queste proprietà vengono ora impostate correttamente quando il metodo SetLineInfo viene usato durante il caricamento di XML.|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Xml.Linq.LoadOptions.SetLineInfo?displayProperty=nameWithType></li></ul>|
