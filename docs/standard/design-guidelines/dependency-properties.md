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
# <a name="dependency-properties"></a><span data-ttu-id="aca5b-102">Proprietà di dipendenza</span><span class="sxs-lookup"><span data-stu-id="aca5b-102">Dependency Properties</span></span>
<span data-ttu-id="aca5b-103">Una proprietà di dipendenza (DP) è una proprietà regolare che archivia il valore in un archivio di proprietà anziché archiviarlo in una variabile di tipo (campo), ad esempio.</span><span class="sxs-lookup"><span data-stu-id="aca5b-103">A dependency property (DP) is a regular property that stores its value in a property store instead of storing it in a type variable (field), for example.</span></span>

 <span data-ttu-id="aca5b-104">Una proprietà di dipendenza associata è un tipo di proprietà di dipendenza modellata come metodi get e set statici che rappresentano le "proprietà" che descrivono le relazioni tra gli oggetti e i relativi contenitori, ad esempio la posizione di un oggetto `Button` in un contenitore di `Panel`).</span><span class="sxs-lookup"><span data-stu-id="aca5b-104">An attached dependency property is a kind of dependency property modeled as static Get and Set methods representing "properties" describing relationships between objects and their containers (e.g., the position of a `Button` object on a `Panel` container).</span></span>

 <span data-ttu-id="aca5b-105">✔️ forniscono le proprietà di dipendenza, se è necessario che le proprietà supportino funzionalità WPF quali lo stile, i trigger, data binding, animazioni, risorse dinamiche ed ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="aca5b-105">✔️ DO provide the dependency properties, if you need the properties to support WPF features such as styling, triggers, data binding, animations, dynamic resources, and inheritance.</span></span>

## <a name="dependency-property-design"></a><span data-ttu-id="aca5b-106">Progettazione delle proprietà di dipendenza</span><span class="sxs-lookup"><span data-stu-id="aca5b-106">Dependency Property Design</span></span>
 <span data-ttu-id="aca5b-107">Quando si implementano le proprietà di dipendenza, ✔️ ereditare da <xref:System.Windows.DependencyObject>o da uno dei relativi sottotipi.</span><span class="sxs-lookup"><span data-stu-id="aca5b-107">✔️ DO inherit from <xref:System.Windows.DependencyObject>, or one of its subtypes, when implementing dependency properties.</span></span> <span data-ttu-id="aca5b-108">Il tipo fornisce un'implementazione molto efficiente di un archivio di proprietà e supporta automaticamente data binding WPF.</span><span class="sxs-lookup"><span data-stu-id="aca5b-108">The type provides a very efficient implementation of a property store and automatically supports WPF data binding.</span></span>

 <span data-ttu-id="aca5b-109">✔️ forniscono una proprietà CLR normale e un campo di sola lettura statico pubblico che archivia un'istanza di <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> per ogni proprietà di dipendenza.</span><span class="sxs-lookup"><span data-stu-id="aca5b-109">✔️ DO provide a regular CLR property and public static read-only field storing an instance of <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> for each dependency property.</span></span>

 <span data-ttu-id="aca5b-110">✔️ implementare le proprietà di dipendenza chiamando i metodi di istanza <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> e <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="aca5b-110">✔️ DO implement dependency properties by calling instance methods <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> and <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.</span></span>

 <span data-ttu-id="aca5b-111">✔️ Denominare il campo statico della proprietà di dipendenza mediante il suffisso del nome della proprietà con "Property".</span><span class="sxs-lookup"><span data-stu-id="aca5b-111">✔️ DO name the dependency property static field by suffixing the name of the property with "Property."</span></span>

 <span data-ttu-id="aca5b-112">❌ non impostare in modo esplicito i valori predefiniti delle proprietà di dipendenza nel codice; impostarli invece nei metadati.</span><span class="sxs-lookup"><span data-stu-id="aca5b-112">❌ DO NOT set default values of dependency properties explicitly in code; set them in metadata instead.</span></span>

 <span data-ttu-id="aca5b-113">Se si imposta in modo esplicito una proprietà predefinita, è possibile impedire che tale proprietà venga impostata da un mezzo implicito, ad esempio uno stile.</span><span class="sxs-lookup"><span data-stu-id="aca5b-113">If you set a property default explicitly, you might prevent that property from being set by some implicit means, such as a styling.</span></span>

 <span data-ttu-id="aca5b-114">❌ non inserire codice nelle funzioni di accesso alle proprietà diverse dal codice standard per accedere al campo statico.</span><span class="sxs-lookup"><span data-stu-id="aca5b-114">❌ DO NOT put code in the property accessors other than the standard code to access the static field.</span></span>

 <span data-ttu-id="aca5b-115">Il codice non viene eseguito se la proprietà viene impostata in modo implicito, ad esempio uno stile, perché lo stile USA direttamente il campo statico.</span><span class="sxs-lookup"><span data-stu-id="aca5b-115">That code won’t execute if the property is set by implicit means, such as a styling, because styling uses the static field directly.</span></span>

 <span data-ttu-id="aca5b-116">❌ non utilizzare le proprietà di dipendenza per archiviare dati protetti.</span><span class="sxs-lookup"><span data-stu-id="aca5b-116">❌ DO NOT use dependency properties to store secure data.</span></span> <span data-ttu-id="aca5b-117">È possibile accedere pubblicamente anche alle proprietà di dipendenza private.</span><span class="sxs-lookup"><span data-stu-id="aca5b-117">Even private dependency properties can be accessed publicly.</span></span>

## <a name="attached-dependency-property-design"></a><span data-ttu-id="aca5b-118">Progettazione della proprietà di dipendenza associata</span><span class="sxs-lookup"><span data-stu-id="aca5b-118">Attached Dependency Property Design</span></span>
 <span data-ttu-id="aca5b-119">Le proprietà di dipendenza descritte nella sezione precedente rappresentano le proprietà intrinseche del tipo dichiarante. ad esempio, la proprietà `Text` è una proprietà di `TextButton`, che lo dichiara.</span><span class="sxs-lookup"><span data-stu-id="aca5b-119">Dependency properties described in the preceding section represent intrinsic properties of the declaring type; for example, the `Text` property is a property of `TextButton`, which declares it.</span></span> <span data-ttu-id="aca5b-120">Un tipo speciale di proprietà di dipendenza è la proprietà di dipendenza associata.</span><span class="sxs-lookup"><span data-stu-id="aca5b-120">A special kind of dependency property is the attached dependency property.</span></span>

 <span data-ttu-id="aca5b-121">Un esempio classico di una proprietà associata è la <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> proprietà.</span><span class="sxs-lookup"><span data-stu-id="aca5b-121">A classic example of an attached property is the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="aca5b-122">La proprietà rappresenta la posizione della colonna del pulsante (non della griglia), ma è pertinente solo se il pulsante è contenuto in una griglia ed è quindi associato ai pulsanti per griglia.</span><span class="sxs-lookup"><span data-stu-id="aca5b-122">The property represents Button’s (not Grid’s) column position, but it is only relevant if the Button is contained in a Grid, and so it's "attached" to Buttons by Grids.</span></span>

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

 <span data-ttu-id="aca5b-123">La definizione di una proprietà associata è analoga a quella di una normale proprietà di dipendenza, ad eccezione del fatto che le funzioni di accesso sono rappresentate dai metodi get e set statici:</span><span class="sxs-lookup"><span data-stu-id="aca5b-123">The definition of an attached property looks mostly like that of a regular dependency property, except that the accessors are represented by static Get and Set methods:</span></span>

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

## <a name="dependency-property-validation"></a><span data-ttu-id="aca5b-124">Convalida della proprietà di dipendenza</span><span class="sxs-lookup"><span data-stu-id="aca5b-124">Dependency Property Validation</span></span>
 <span data-ttu-id="aca5b-125">Le proprietà spesso implementano la cosiddetta convalida.</span><span class="sxs-lookup"><span data-stu-id="aca5b-125">Properties often implement what is called validation.</span></span> <span data-ttu-id="aca5b-126">La logica di convalida viene eseguita quando viene effettuato un tentativo di modificare il valore di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="aca5b-126">Validation logic executes when an attempt is made to change the value of a property.</span></span>

 <span data-ttu-id="aca5b-127">Sfortunatamente le funzioni di accesso alle proprietà di dipendenza non possono contenere codice di convalida arbitrario.</span><span class="sxs-lookup"><span data-stu-id="aca5b-127">Unfortunately dependency property accessors cannot contain arbitrary validation code.</span></span> <span data-ttu-id="aca5b-128">Al contrario, la logica di convalida delle proprietà di dipendenza deve essere specificata durante la registrazione della proprietà.</span><span class="sxs-lookup"><span data-stu-id="aca5b-128">Instead, dependency property validation logic needs to be specified during property registration.</span></span>

 <span data-ttu-id="aca5b-129">❌ non inserire la logica di convalida della proprietà di dipendenza nelle funzioni di accesso della proprietà.</span><span class="sxs-lookup"><span data-stu-id="aca5b-129">❌ DO NOT put dependency property validation logic in the property’s accessors.</span></span> <span data-ttu-id="aca5b-130">Al contrario, passare un callback di convalida al metodo `DependencyProperty.Register`.</span><span class="sxs-lookup"><span data-stu-id="aca5b-130">Instead, pass a validation callback to `DependencyProperty.Register` method.</span></span>

## <a name="dependency-property-change-notifications"></a><span data-ttu-id="aca5b-131">Notifiche di modifica delle proprietà di dipendenza</span><span class="sxs-lookup"><span data-stu-id="aca5b-131">Dependency Property Change Notifications</span></span>
 <span data-ttu-id="aca5b-132">❌ non implementare la logica di notifica delle modifiche nelle funzioni di accesso alle proprietà di dipendenza.</span><span class="sxs-lookup"><span data-stu-id="aca5b-132">❌ DO NOT implement change notification logic in dependency property accessors.</span></span> <span data-ttu-id="aca5b-133">Le proprietà di dipendenza dispongono di una funzionalità di notifica delle modifiche incorporata che deve essere utilizzata fornendo un callback di notifica delle modifiche al <xref:System.Windows.PropertyMetadata>.</span><span class="sxs-lookup"><span data-stu-id="aca5b-133">Dependency properties have a built-in change notifications feature that must be used by supplying a change notification callback to the <xref:System.Windows.PropertyMetadata>.</span></span>

## <a name="dependency-property-value-coercion"></a><span data-ttu-id="aca5b-134">Coercizione del valore della proprietà di dipendenza</span><span class="sxs-lookup"><span data-stu-id="aca5b-134">Dependency Property Value Coercion</span></span>
 <span data-ttu-id="aca5b-135">La coercizione delle proprietà viene eseguita quando il valore assegnato a un setter di proprietà viene modificato dal setter prima che l'archivio delle proprietà venga effettivamente modificato.</span><span class="sxs-lookup"><span data-stu-id="aca5b-135">Property coercion takes place when the value given to a property setter is modified by the setter before the property store is actually modified.</span></span>

 <span data-ttu-id="aca5b-136">❌ non implementare la logica di coercizione nelle funzioni di accesso alle proprietà di dipendenza.</span><span class="sxs-lookup"><span data-stu-id="aca5b-136">❌ DO NOT implement coercion logic in dependency property accessors.</span></span>

 <span data-ttu-id="aca5b-137">Le proprietà di dipendenza hanno una funzionalità di coercizione incorporata e possono essere usate fornendo un callback di coercizione al `PropertyMetadata`.</span><span class="sxs-lookup"><span data-stu-id="aca5b-137">Dependency properties have a built-in coercion feature, and it can be used by supplying a coercion callback to the `PropertyMetadata`.</span></span>

 <span data-ttu-id="aca5b-138">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="aca5b-138">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="aca5b-139">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="aca5b-139">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="aca5b-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aca5b-140">See also</span></span>

- [<span data-ttu-id="aca5b-141">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="aca5b-141">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="aca5b-142">Modelli di progettazione comuni</span><span class="sxs-lookup"><span data-stu-id="aca5b-142">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)
