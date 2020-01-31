---
title: Proprietà di dipendenza
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
ms.openlocfilehash: e1372b75cb6501f8bc3fec913364e9d80157ad83
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741730"
---
# <a name="dependency-properties"></a>Proprietà di dipendenza
Una proprietà di dipendenza (DP) è una proprietà regolare che archivia il valore in un archivio di proprietà anziché archiviarlo in una variabile di tipo (campo), ad esempio.

 Una proprietà di dipendenza associata è un tipo di proprietà di dipendenza modellata come metodi get e set statici che rappresentano le "proprietà" che descrivono le relazioni tra gli oggetti e i relativi contenitori, ad esempio la posizione di un oggetto `Button` in un contenitore di `Panel`).

 ✔️ forniscono le proprietà di dipendenza, se è necessario che le proprietà supportino funzionalità WPF quali lo stile, i trigger, data binding, animazioni, risorse dinamiche ed ereditarietà.

## <a name="dependency-property-design"></a>Progettazione delle proprietà di dipendenza
 Quando si implementano le proprietà di dipendenza, ✔️ ereditare da <xref:System.Windows.DependencyObject>o da uno dei relativi sottotipi. Il tipo fornisce un'implementazione molto efficiente di un archivio di proprietà e supporta automaticamente data binding WPF.

 ✔️ forniscono una proprietà CLR normale e un campo di sola lettura statico pubblico che archivia un'istanza di <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> per ogni proprietà di dipendenza.

 ✔️ implementare le proprietà di dipendenza chiamando i metodi di istanza <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> e <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.

 ✔️ Denominare il campo statico della proprietà di dipendenza mediante il suffisso del nome della proprietà con "Property".

 ❌ non impostare in modo esplicito i valori predefiniti delle proprietà di dipendenza nel codice; impostarli invece nei metadati.

 Se si imposta in modo esplicito una proprietà predefinita, è possibile impedire che tale proprietà venga impostata da un mezzo implicito, ad esempio uno stile.

 ❌ non inserire codice nelle funzioni di accesso alle proprietà diverse dal codice standard per accedere al campo statico.

 Il codice non viene eseguito se la proprietà viene impostata in modo implicito, ad esempio uno stile, perché lo stile USA direttamente il campo statico.

 ❌ non utilizzare le proprietà di dipendenza per archiviare dati protetti. È possibile accedere pubblicamente anche alle proprietà di dipendenza private.

## <a name="attached-dependency-property-design"></a>Progettazione della proprietà di dipendenza associata
 Le proprietà di dipendenza descritte nella sezione precedente rappresentano le proprietà intrinseche del tipo dichiarante. ad esempio, la proprietà `Text` è una proprietà di `TextButton`, che lo dichiara. Un tipo speciale di proprietà di dipendenza è la proprietà di dipendenza associata.

 Un esempio classico di una proprietà associata è la <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> proprietà. La proprietà rappresenta la posizione della colonna del pulsante (non della griglia), ma è pertinente solo se il pulsante è contenuto in una griglia ed è quindi associato ai pulsanti per griglia.

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

 La definizione di una proprietà associata è analoga a quella di una normale proprietà di dipendenza, ad eccezione del fatto che le funzioni di accesso sono rappresentate dai metodi get e set statici:

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

## <a name="dependency-property-validation"></a>Convalida della proprietà di dipendenza
 Le proprietà spesso implementano la cosiddetta convalida. La logica di convalida viene eseguita quando viene effettuato un tentativo di modificare il valore di una proprietà.

 Sfortunatamente le funzioni di accesso alle proprietà di dipendenza non possono contenere codice di convalida arbitrario. Al contrario, la logica di convalida delle proprietà di dipendenza deve essere specificata durante la registrazione della proprietà.

 ❌ non inserire la logica di convalida della proprietà di dipendenza nelle funzioni di accesso della proprietà. Al contrario, passare un callback di convalida al metodo `DependencyProperty.Register`.

## <a name="dependency-property-change-notifications"></a>Notifiche di modifica delle proprietà di dipendenza
 ❌ non implementare la logica di notifica delle modifiche nelle funzioni di accesso alle proprietà di dipendenza. Le proprietà di dipendenza dispongono di una funzionalità di notifica delle modifiche incorporata che deve essere utilizzata fornendo un callback di notifica delle modifiche al <xref:System.Windows.PropertyMetadata>.

## <a name="dependency-property-value-coercion"></a>Coercizione del valore della proprietà di dipendenza
 La coercizione delle proprietà viene eseguita quando il valore assegnato a un setter di proprietà viene modificato dal setter prima che l'archivio delle proprietà venga effettivamente modificato.

 ❌ non implementare la logica di coercizione nelle funzioni di accesso alle proprietà di dipendenza.

 Le proprietà di dipendenza hanno una funzionalità di coercizione incorporata e possono essere usate fornendo un callback di coercizione al `PropertyMetadata`.

 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
- [Modelli di progettazione comuni](../../../docs/standard/design-guidelines/common-design-patterns.md)
