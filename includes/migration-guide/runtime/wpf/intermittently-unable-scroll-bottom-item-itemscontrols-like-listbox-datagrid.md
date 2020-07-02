---
ms.openlocfilehash: b92dc8a1c48e83846c3d9a1d86e66629f31b7722
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622021"
---
### <a name="intermittently-unable-to-scroll-to-bottom-item-in-itemscontrols-like-listbox-and-datagrid-when-using-custom-datatemplates"></a>Di tanti in tanto non è possibile scorrere fino all'elemento inferiore in ItemsControls (ad esempio ListBox e DataGrid) quando si usano DataTemplates personalizzati

#### <a name="details"></a>Dettagli

In alcuni casi, a causa di un bug in .NET Framework 4.5 i controlli ItemsControls (come <xref:System.Windows.Controls.ListBox?displayProperty=fullName>, <xref:System.Windows.Controls.ComboBox?displayProperty=fullName>, <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> e così via) non scorrono fino all'elemento inferiore quando si usano DataTemplates personalizzati. Lo scorrimento funzionerà se si esegue un secondo tentativo dopo uno scorrimento verso l'alto.

#### <a name="suggestion"></a>Suggerimento

Questo problema è stato corretto in .NET Framework 4.5.2 e può essere risolto eseguendo l'aggiornamento a tale versione di .NET Framework o a una versione successiva. In alternativa, gli utenti possono trascinare le barre di scorrimento fino agli elementi finali di queste raccolte, ma potrebbe essere necessario provare due volte per completare l'operazione correttamente.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.5|
|Type|Runtime|
