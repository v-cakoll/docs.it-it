---
title: "Proprietà di dipendenza"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 21e2026e7ce0f2dcf1ffc9a328b1bb9630cd8fbf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="dependency-properties"></a>Proprietà di dipendenza
Una proprietà di dipendenza (DP) è una proprietà normale che archivia il valore in un archivio di proprietà anziché archiviare i dati in una variabile di tipo (campo), ad esempio.  
  
 Una proprietà di dipendenza collegata è un tipo di proprietà di dipendenza modellata come metodi statici di Get e Set che rappresenta "proprietà" descrizione delle relazioni tra oggetti e i relativi contenitori (ad esempio, la posizione di un `Button` oggetto un `Panel` contenitore).  
  
 **✓ SI** forniscono le proprietà di dipendenza, se necessario, le proprietà per supportare le funzionalità WPF, ad esempio stile, trigger, data binding, animazioni, le risorse dinamiche ed ereditarietà.  
  
## <a name="dependency-property-design"></a>Progettazione di proprietà di dipendenza  
 **✓ SI** ereditare <xref:System.Windows.DependencyObject>, o uno dei relativi sottotipi, quando si implementa le proprietà di dipendenza. Il tipo fornisce un'implementazione estremamente efficiente di un archivio di proprietà e l'associazione dati WPF sono automaticamente supportati.  
  
 **✓ SI** fornire una proprietà CLR regolare e un campo statico pubblico sola lettura e l'archiviazione di un'istanza di <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> per ogni proprietà di dipendenza.  
  
 **✓ SI** implementare le proprietà di dipendenza chiamando i metodi di istanza <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> e <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.  
  
 **✓ SI** nome campo statico della proprietà di dipendenza, aggiungendo il nome della proprietà con "Proprietà".  
  
 **X non** impostare valori predefiniti delle proprietà di dipendenza in modo esplicito nel codice; impostarle nei metadati.  
  
 Se si imposta un valore predefinito di proprietà in modo esplicito, è necessario impedire tale proprietà di impostazione in modo implicito, ad esempio uno stile.  
  
 **X non** inserire codice nelle funzioni di proprietà accesso diversi dal codice standard per accedere al campo statico.  
  
 Che il codice non verrà eseguito se la proprietà è impostata in modo implicito, ad esempio uno stile, perché l'applicazione degli stili, il campo statico viene utilizzato direttamente.  
  
 **X non** utilizzare le proprietà di dipendenza per memorizzare dati protetti. Le proprietà di dipendenza anche private sono accessibili pubblicamente.  
  
## <a name="attached-dependency-property-design"></a>Progettazione di proprietà di dipendenza collegata  
 Proprietà di dipendenza descritte nella sezione precedente rappresentano le proprietà intrinseche del tipo dichiarante. ad esempio, il `Text` è una proprietà del `TextButton`, che dichiara. Un tipo speciale di proprietà di dipendenza è la proprietà di dipendenza associata.  
  
 Un esempio classico di una proprietà associata è di <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> proprietà. La proprietà rappresenta la posizione di colonna del pulsante (non della griglia), ma rilevante solo se il pulsante è contenuto in una griglia e quindi è "connesso" a pulsanti per le griglie.  
  
```  
<Grid>  
    <Grid.ColumnDefinitions>  
        <ColumnDefinition />  
        <ColumnDefinition />  
    </Grid.ColumnDefinitions>  
  
    <Button Grid.Column="0">Click</Button>  
    <Button Grid.Column="1">Clack</Button>  
</Grid>  
```  
  
 La definizione di una proprietà associata è principalmente simile a quella di una proprietà di dipendenza normale, ad eccezione del fatto che le funzioni di accesso sono rappresentati dai metodi Get e Set statici:  
  
```  
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
  
 **X non** inserire logica di convalida di proprietà di dipendenza in funzioni di accesso della proprietà. Al contrario, passare a un callback di convalida `DependencyProperty.Register` metodo.  
  
## <a name="dependency-property-change-notifications"></a>Notifiche di modifica di proprietà di dipendenza  
 **X non** implementare la logica di notifica di modifica nell'accesso della proprietà di dipendenza. Le proprietà di dipendenza sono una funzionalità di notifiche di modifica predefinito che deve essere usata da fornire un callback di notifica di modifica per il <xref:System.Windows.PropertyMetadata>.  
  
## <a name="dependency-property-value-coercion"></a>Coercizione del valore di proprietà di dipendenza  
 Coercizione di proprietà ha luogo quando il valore assegnato a un setter di proprietà viene modificato dal metodo di impostazione prima che l'archivio delle proprietà venga effettivamente modificata.  
  
 **X non** implementare la logica di coercizione nell'accesso della proprietà di dipendenza.  
  
 Le proprietà di dipendenza sono una funzionalità di coercizione incorporata e può essere utilizzato, fornendo un callback la coercizione di `PropertyMetadata`.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
 [Modelli di progettazione comuni](../../../docs/standard/design-guidelines/common-design-patterns.md)
