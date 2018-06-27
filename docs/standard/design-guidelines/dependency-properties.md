---
title: Proprietà di dipendenza
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7398202cc265fbd55b9bf0b5a53367dedcab57b0
ms.sourcegitcommit: ed7b4b9b77d35e94a35a2634e8c874f46603fb2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2018
ms.locfileid: "36948485"
---
# <a name="dependency-properties"></a>Proprietà di dipendenza
Una proprietà di dipendenza (DP) è una proprietà normale che archivia il valore in un archivio di proprietà anziché archiviare i dati in una variabile di tipo (campo), ad esempio.  
  
 Una proprietà di dipendenza collegata è un tipo di proprietà di dipendenza modellata come metodi statici di Get e Set che rappresenta "proprietà" descrizione delle relazioni tra oggetti e i relativi contenitori (ad esempio, la posizione di un `Button` dell'oggetto su un `Panel` contenitore).  
  
 **✓ SI** forniscono le proprietà di dipendenza, se è necessario le proprietà per supportare le funzionalità WPF, ad esempio stile, trigger, data binding, animazioni, le risorse dinamiche ed ereditarietà.  
  
## <a name="dependency-property-design"></a>Progettazione di proprietà di dipendenza  
 **✓ SI** ereditare <xref:System.Windows.DependencyObject>, o uno dei sottotipi, quando si implementa le proprietà di dipendenza. Il tipo fornisce un'implementazione estremamente efficiente di un archivio delle proprietà e il data binding WPF sono automaticamente supportati.  
  
 **✓ SI** fornire un proprietà CLR regolare e un campo statico pubblico sola lettura e l'archiviazione di un'istanza di <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> per ogni proprietà di dipendenza.  
  
 **✓ SI** implementare le proprietà di dipendenza chiamando i metodi di istanza <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> e <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.  
  
 **✓ SI** denominare il campo statico di proprietà di dipendenza aggiungendo il nome della proprietà con "Proprietà".  
  
 **X non** impostare valori predefiniti delle proprietà di dipendenza in modo esplicito nel codice; impostarle nei metadati.  
  
 Se si imposta un valore predefinito di proprietà in modo esplicito, è necessario impedire tale proprietà di viene impostata in modo implicito, ad esempio uno stile.  
  
 **X non** inserire codice in funzioni di accesso diversi da code standard per accedere al campo statico.  
  
 Che il codice non verrà eseguito se la proprietà è impostata in modo implicito, ad esempio uno stile, perché l'applicazione degli stili, il campo statico viene utilizzato direttamente.  
  
 **X non** utilizzare le proprietà di dipendenza per archiviare i dati protetti. Le proprietà di dipendenza anche privati sono accessibili pubblicamente.  
  
## <a name="attached-dependency-property-design"></a>Progettazione di proprietà di dipendenza collegata  
 Proprietà di dipendenza descritte nella sezione precedente rappresentano proprietà intrinseche del tipo dichiarante. ad esempio, il `Text` è una proprietà di `TextButton`, che lo dichiara. Un tipo speciale di proprietà di dipendenza è la proprietà di dipendenza collegata.  
  
 Un esempio classico di una proprietà associata è il <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> proprietà. La proprietà rappresenta la posizione di colonna del pulsante (non della griglia), ma rilevante solo se il pulsante è contenuto in una griglia, quindi è "connesso" a pulsanti da griglie.  
  
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
  
 La definizione di una proprietà associata è simile principalmente a quello di una proprietà di dipendenza normale, ad eccezione del fatto che le funzioni di accesso sono rappresentati dai metodi Get e Set statici:  
  
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
 Proprietà implementano spesso cosiddetto convalida. La logica di convalida viene eseguita quando viene effettuato un tentativo di modificare il valore di una proprietà.  
  
 Sfortunatamente accesso della proprietà di dipendenza non può contenere codice di convalida arbitraria. Al contrario, logica di convalida di proprietà di dipendenza deve essere specificato durante la registrazione di proprietà.  
  
 **X non** inserire logica di convalida di proprietà di dipendenza in funzioni di accesso della proprietà. Al contrario, passare un callback di convalida per `DependencyProperty.Register` metodo.  
  
## <a name="dependency-property-change-notifications"></a>Notifiche di modifica proprietà di dipendenza  
 **X non** implementare la logica di notifica di modifica nell'accesso della proprietà di dipendenza. Le proprietà di dipendenza sono una funzionalità di notifiche di modifica incorporate che deve essere usata da fornire un callback di notifica di modifica per il <xref:System.Windows.PropertyMetadata>.  
  
## <a name="dependency-property-value-coercion"></a>Coercizione del valore di proprietà di dipendenza  
 Coercizione di proprietà ha luogo quando il valore in base a un setter di proprietà viene modificato dal setter prima che venga effettivamente modificata l'archivio delle proprietà.  
  
 **X non** implementare la logica di coercizione nell'accesso della proprietà di dipendenza.  
  
 Le proprietà di dipendenza sono una funzionalità di coercizione incorporata e può essere utilizzato, fornendo un callback la coercizione di `PropertyMetadata`.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. dal [Framework linee guida di progettazione: convenzioni, idiomi e modelli per le librerie .NET riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
 [Modelli di progettazione comuni](../../../docs/standard/design-guidelines/common-design-patterns.md)
