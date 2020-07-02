---
ms.openlocfilehash: 35fc4782ebbba33f5fc6668712af9d89d00cafe9
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614971"
---
### <a name="wpf-changing-a-primary-key-when-displaying-ado-data-in-a-masterdetail-scenario"></a>WPF modifica una chiave primaria quando si visualizzano dati ADO in uno scenario master/dettagli

#### <a name="details"></a>Dettagli

Si supponga di avere una raccolta ADO di elementi di tipo `Order`, con una relazione denominata &quot;OrderDetails&quot; che la mette in relazione con una raccolta di elementi di tipo `Detail` tramite la chiave primaria &quot;OrderID&quot;. Nell'app WPF, è possibile associare un elenco ai dettagli per un ordine specifico:

```xaml
<ListBox ItemsSource="{Binding Path=OrderDetails}" >
```

dove DataContext è un `Order`. WPF ottiene il valore della `OrderDetails` proprietà, una raccolta D di tutti gli `Detail` elementi la cui `OrderID` corrispondenza corrisponde a dell' `OrderID` elemento Master. La modifica del comportamento si verifica quando si modifica la chiave primaria `OrderID` dell'elemento Master. ADO modifica automaticamente l'`OrderID` di ognuno dei record interessati nella raccolta dei dettagli, vale a dire quelli copiati nella raccolta D.  Cosa accade a D?

- Comportamento precedente: la raccolta D è deselezionata. L'elemento master *non* genera una notifica della modifica per la proprietà `OrderDetails`. L'oggetto ListBox continua a usare la raccolta D, che ora è vuota.
- Nuovo comportamento: la raccolta D rimane invariata. Ognuno dei relativi elementi genera una notifica della modifica della proprietà `OrderID`. L'oggetto ListBox continua a usare la raccolta D e visualizza i dettagli con il nuovo `OrderID`. WPF implementa il nuovo comportamento creando la raccolta D in un modo diverso: chiamando il metodo ADO <xref:System.Data.DataRowView.CreateChildView(System.Data.DataRelation,System.Boolean)?displayProperty=nameWithType> con l'argomento `followParent` impostato su `true`.

#### <a name="suggestion"></a>Suggerimento

Per ottenere il nuovo comportamento, le app usano l'opzione AppContext.

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Data.DoNotUseFollowParentWhenBindingToADODataRelation=false"/>
  </runtime>
</configuration>
```

Per impostazione predefinita, l'opzione è impostata su `true` (comportamento precedente) per le app destinate a .NET 4.7.1 o versione precedente, e su `false` (nuovo comportamento) per le app destinate a .NET 4.7.2 o versione successiva.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Minorenne       |
| Version | 4.7.2       |
| Type    | Ridestinazione |
