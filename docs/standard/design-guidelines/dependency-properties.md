---
title: Proprietà di dipendenza
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
author: KrzysztofCwalina
ms.openlocfilehash: 52d7a69a3f52c67ebff3f3db1daf0790e995913a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54721981"
---
# <a name="dependency-properties"></a>Proprietà di dipendenza
Una proprietà di dipendenza (DP) è una proprietà regolare che archivia il relativo valore in un archivio di proprietà anziché archiviare i dati in una variabile di tipo (campo), ad esempio.  
  
 Una proprietà di dipendenza collegata è un tipo di proprietà di dipendenza modellate come metodi statici di Get e Set che rappresenta "properties", che descrivono le relazioni tra oggetti e i relativi contenitori (ad esempio, la posizione di un `Button` dell'oggetto su un `Panel` contenitore).  
  
 **✓ DO** forniscono le proprietà di dipendenza, se è necessario le proprietà per supportare le funzionalità WPF, ad esempio stile, trigger, data binding, animazioni, le risorse dinamiche ed ereditarietà.  
  
## <a name="dependency-property-design"></a>Progettazione di proprietà di dipendenza  
 **✓ DO** ereditare <xref:System.Windows.DependencyObject>, o uno dei sottotipi, quando si implementa le proprietà di dipendenza. Il tipo fornisce un'implementazione estremamente efficiente di un archivio di proprietà e supporta automaticamente l'associazione dati WPF.  
  
 **✓ DO** fornire un proprietà CLR regolare e un campo statico pubblico sola lettura e l'archiviazione di un'istanza di <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> per ogni proprietà di dipendenza.  
  
 **✓ DO** implementare le proprietà di dipendenza chiamando i metodi di istanza <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> e <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.  
  
 **✓ DO** denominare il campo statico di proprietà di dipendenza aggiungendo il nome della proprietà con "Proprietà".  
  
 **X DO NOT** impostare valori predefiniti delle proprietà di dipendenza in modo esplicito nel codice; impostarle nei metadati.  
  
 Si imposta un valore predefinito di proprietà in modo esplicito, si potrebbe impedire tale proprietà viene impostata in modo implicito, ad esempio un'applicazione di stili.  
  
 **X DO NOT** inserire codice in funzioni di accesso diversi da code standard per accedere al campo statico.  
  
 Che il codice non verrà eseguito se la proprietà è impostata in modo implicito, ad esempio un'applicazione di stili, poiché lo stile Usa direttamente il campo statico.  
  
 **X DO NOT** utilizzare le proprietà di dipendenza per archiviare i dati protetti. Le proprietà di dipendenza persino privati sono accessibili pubblicamente.  
  
## <a name="attached-dependency-property-design"></a>Progettazione di proprietà di dipendenza collegata  
 Le proprietà di dipendenza descritte nella precedente sezione rappresentano le proprietà intrinseche del tipo dichiarante. ad esempio, il `Text` è una proprietà del `TextButton`, che lo dichiara. Un tipo speciale di proprietà di dipendenza è la proprietà di dipendenza collegata.  
  
 Un esempio classico di una proprietà associata è di <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> proprietà. La proprietà rappresenta la posizione di colonna del pulsante (non della griglia), ma rilevante solo se il pulsante è contenuto in una griglia, quindi è "collegato" ai pulsanti da griglie.  
  
```xaml
<Grid>  
    <Grid.ColumnDefinitions>  
        <ColumnDefinition />  
        <ColumnDefinition />  
    </Grid.ColumnDefinitions>  
  
    <Button Grid.Column="0">Click</Button>  
    <Button Grid.Column="1">Clack</Button>  
</Grid>  
```  
  
 La definizione di una proprietà associata è simile per lo più simile a quella di una proprietà di dipendenza normale, ad eccezione del fatto che le funzioni di accesso sono rappresentati dai metodi statici di Get e Set:  
  
```csharp
public class Grid {  
  
    public static int GetColumn(DependencyObject obj) {  
        return (int)obj.GetValue(ColumnProperty);  
    }  
  
    public static void SetColumn(DependencyObject obj, int value) {  
        obj.SetValue(ColumnProperty,value);  
    }  
  
    public static readonly DependencyProperty ColumnProperty =  
        DependencyProperty.RegisterAttached(  
            "Column",  
            typeof(int),  
            typeof(Grid)  
    );  
}  
```  
  
## <a name="dependency-property-validation"></a>Convalida delle proprietà di dipendenza  
 Proprietà implementeranno cosiddetta convalida. La logica di convalida viene eseguita quando viene effettuato un tentativo di modificare il valore di una proprietà.  
  
 Purtroppo accesso della proprietà di dipendenza non può contenere codice di convalida arbitraria. Al contrario, la logica di convalida di proprietà di dipendenza deve essere specificata durante la registrazione della proprietà.  
  
 **X DO NOT** inserire logica di convalida di proprietà di dipendenza in funzioni di accesso della proprietà. In alternativa, passare un callback di convalida a `DependencyProperty.Register` (metodo).  
  
## <a name="dependency-property-change-notifications"></a>Notifiche di modifica proprietà di dipendenza  
 **X DO NOT** implementare la logica di notifica di modifica nell'accesso della proprietà di dipendenza. Le proprietà di dipendenza dispongono di una funzionalità di notifiche di modifica predefinito che deve essere usata specificando un callback di notifica di modifica per il <xref:System.Windows.PropertyMetadata>.  
  
## <a name="dependency-property-value-coercion"></a>Coercizione del valore di proprietà di dipendenza  
 Coercizione di proprietà viene eseguita quando viene modificato il valore assegnato a un setter delle proprietà per il setter prima che venga effettivamente modificata l'archivio delle proprietà.  
  
 **X DO NOT** implementare la logica di coercizione nell'accesso della proprietà di dipendenza.  
  
 Le proprietà di dipendenza dispongono di una funzionalità di coercizione incorporata, e può essere usato specificando un callback di coercizione per il `PropertyMetadata`.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
- [Modelli di progettazione comuni](../../../docs/standard/design-guidelines/common-design-patterns.md)
