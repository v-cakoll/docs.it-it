---
ms.openlocfilehash: 9c2ee4ba66deb7c3b33698963add2b8a7e70069f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803217"
---
### <a name="intermittently-unable-to-scroll-to-bottom-item-in-itemscontrols-like-listbox-and-datagrid-when-using-custom-datatemplates"></a>Di tanti in tanto non è possibile scorrere fino all'elemento inferiore in ItemsControls (ad esempio ListBox e DataGrid) quando si usano DataTemplates personalizzati

|   |   |
|---|---|
|Dettagli|In alcuni casi, a causa di un bug in .NET Framework 4.5 i controlli ItemsControls (come <xref:System.Windows.Controls.ListBox?displayProperty=name>, <xref:System.Windows.Controls.ComboBox?displayProperty=name>, <xref:System.Windows.Controls.DataGrid?displayProperty=name> e così via) non scorrono fino all'elemento inferiore quando si usano DataTemplates personalizzati. Lo scorrimento funzionerà se si esegue un secondo tentativo dopo uno scorrimento verso l'alto.|
|Suggerimento|Questo problema è stato corretto in .NET Framework 4.5.2 e può essere risolto eseguendo l'aggiornamento a tale versione di .NET Framework o a una versione successiva. In alternativa, gli utenti possono trascinare le barre di scorrimento fino agli elementi finali di queste raccolte, ma potrebbe essere necessario provare due volte per completare l'operazione correttamente.|
|Scope|Minorenne|
|Versione|4.5|
|Type|Runtime|
