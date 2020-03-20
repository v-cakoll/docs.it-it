---
ms.openlocfilehash: e39b4e85b47902babac7a22a93aa64c2f86ef01f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804682"
---
### <a name="dataobjectgetdata-now-retrieves-data-as-utf-8"></a>DataObject.GetData ora recupera i dati come UTF-8

|   |   |
|---|---|
|Dettagli|Per le app destinate a .NET Framework 4 o che vengono eseguite in .NET Framework 4.5.1 o in versioni precedenti, <code>DataObject.GetData</code> recupera dati in formato HTML sotto forma di stringa ASCII. Di conseguenza, i caratteri non ASCII, ovvero quelli i cui codici ASCII sono maggiori di 0x7F, vengono rappresentati da due caratteri casuali.<p/>Per le app destinate a .NET Framework 4.5 o versione successiva ed eseguite in .NET Framework 4.5.2, <code>DataObject.GetData</code> recupera i dati in formato HTML come UTF-8, che rappresenta correttamente i caratteri con codici maggiori di 0x7F.|
|Suggerimento|Se è stata implementata una soluzione alternativa per il problema di codifica con le stringhe in formato HTML, ad esempio codificando in modo esplicito la stringa HTML recuperata dagli Appunti passandola a <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=name>, e si intende ridestinare l'app dalla versione 4 alla versione 4.5, è necessario rimuovere questa soluzione alternativa. Se per qualche motivo è necessario il comportamento precedente, l'app può essere destinata a .NET Framework 4.0 per ottenere tale comportamento.|
|Scope|Microsoft Edge|
|Versione|4.5.2|
|Type|Ridestinazione|
|API interessate|<ul><li><xref:System.Windows.DataObject.GetData(System.String)?displayProperty=nameWithType></li><li><xref:System.Windows.DataObject.GetData(System.Type)?displayProperty=nameWithType></li><li><xref:System.Windows.DataObject.GetData(System.String,System.Boolean)?displayProperty=nameWithType></li></ul>|
