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
# <a name="dependency-properties"></a><span data-ttu-id="2195a-102">Proprietà di dipendenza</span><span class="sxs-lookup"><span data-stu-id="2195a-102">Dependency Properties</span></span>
<span data-ttu-id="2195a-103">Una proprietà di dipendenza (DP) è una proprietà normale che archivia il valore in un archivio di proprietà anziché archiviare i dati in una variabile di tipo (campo), ad esempio.</span><span class="sxs-lookup"><span data-stu-id="2195a-103">A dependency property (DP) is a regular property that stores its value in a property store instead of storing it in a type variable (field), for example.</span></span>  
  
 <span data-ttu-id="2195a-104">Una proprietà di dipendenza collegata è un tipo di proprietà di dipendenza modellata come metodi statici di Get e Set che rappresenta "proprietà" descrizione delle relazioni tra oggetti e i relativi contenitori (ad esempio, la posizione di un `Button` dell'oggetto su un `Panel` contenitore).</span><span class="sxs-lookup"><span data-stu-id="2195a-104">An attached dependency property is a kind of dependency property modeled as static Get and Set methods representing "properties" describing relationships between objects and their containers (e.g., the position of a `Button` object on a `Panel` container).</span></span>  
  
 <span data-ttu-id="2195a-105">**✓ SI** forniscono le proprietà di dipendenza, se è necessario le proprietà per supportare le funzionalità WPF, ad esempio stile, trigger, data binding, animazioni, le risorse dinamiche ed ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="2195a-105">**✓ DO** provide the dependency properties, if you need the properties to support WPF features such as styling, triggers, data binding, animations, dynamic resources, and inheritance.</span></span>  
  
## <a name="dependency-property-design"></a><span data-ttu-id="2195a-106">Progettazione di proprietà di dipendenza</span><span class="sxs-lookup"><span data-stu-id="2195a-106">Dependency Property Design</span></span>  
 <span data-ttu-id="2195a-107">**✓ SI** ereditare <xref:System.Windows.DependencyObject>, o uno dei sottotipi, quando si implementa le proprietà di dipendenza.</span><span class="sxs-lookup"><span data-stu-id="2195a-107">**✓ DO** inherit from <xref:System.Windows.DependencyObject>, or one of its subtypes, when implementing dependency properties.</span></span> <span data-ttu-id="2195a-108">Il tipo fornisce un'implementazione estremamente efficiente di un archivio delle proprietà e il data binding WPF sono automaticamente supportati.</span><span class="sxs-lookup"><span data-stu-id="2195a-108">The type provides a very efficient implementation of a property store and automatically supports WPF data binding.</span></span>  
  
 <span data-ttu-id="2195a-109">**✓ SI** fornire un proprietà CLR regolare e un campo statico pubblico sola lettura e l'archiviazione di un'istanza di <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> per ogni proprietà di dipendenza.</span><span class="sxs-lookup"><span data-stu-id="2195a-109">**✓ DO** provide a regular CLR property and public static read-only field storing an instance of <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> for each dependency property.</span></span>  
  
 <span data-ttu-id="2195a-110">**✓ SI** implementare le proprietà di dipendenza chiamando i metodi di istanza <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> e <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2195a-110">**✓ DO** implement dependency properties by calling instance methods <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> and <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="2195a-111">**✓ SI** denominare il campo statico di proprietà di dipendenza aggiungendo il nome della proprietà con "Proprietà".</span><span class="sxs-lookup"><span data-stu-id="2195a-111">**✓ DO** name the dependency property static field by suffixing the name of the property with "Property."</span></span>  
  
 <span data-ttu-id="2195a-112">**X non** impostare valori predefiniti delle proprietà di dipendenza in modo esplicito nel codice; impostarle nei metadati.</span><span class="sxs-lookup"><span data-stu-id="2195a-112">**X DO NOT** set default values of dependency properties explicitly in code; set them in metadata instead.</span></span>  
  
 <span data-ttu-id="2195a-113">Se si imposta un valore predefinito di proprietà in modo esplicito, è necessario impedire tale proprietà di viene impostata in modo implicito, ad esempio uno stile.</span><span class="sxs-lookup"><span data-stu-id="2195a-113">If you set a property default explicitly, you might prevent that property from being set by some implicit means, such as a styling.</span></span>  
  
 <span data-ttu-id="2195a-114">**X non** inserire codice in funzioni di accesso diversi da code standard per accedere al campo statico.</span><span class="sxs-lookup"><span data-stu-id="2195a-114">**X DO NOT** put code in the property accessors other than the standard code to access the static field.</span></span>  
  
 <span data-ttu-id="2195a-115">Che il codice non verrà eseguito se la proprietà è impostata in modo implicito, ad esempio uno stile, perché l'applicazione degli stili, il campo statico viene utilizzato direttamente.</span><span class="sxs-lookup"><span data-stu-id="2195a-115">That code won’t execute if the property is set by implicit means, such as a styling, because styling uses the static field directly.</span></span>  
  
 <span data-ttu-id="2195a-116">**X non** utilizzare le proprietà di dipendenza per archiviare i dati protetti.</span><span class="sxs-lookup"><span data-stu-id="2195a-116">**X DO NOT** use dependency properties to store secure data.</span></span> <span data-ttu-id="2195a-117">Le proprietà di dipendenza anche privati sono accessibili pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="2195a-117">Even private dependency properties can be accessed publicly.</span></span>  
  
## <a name="attached-dependency-property-design"></a><span data-ttu-id="2195a-118">Progettazione di proprietà di dipendenza collegata</span><span class="sxs-lookup"><span data-stu-id="2195a-118">Attached Dependency Property Design</span></span>  
 <span data-ttu-id="2195a-119">Proprietà di dipendenza descritte nella sezione precedente rappresentano proprietà intrinseche del tipo dichiarante. ad esempio, il `Text` è una proprietà di `TextButton`, che lo dichiara.</span><span class="sxs-lookup"><span data-stu-id="2195a-119">Dependency properties described in the preceding section represent intrinsic properties of the declaring type; for example, the `Text` property is a property of `TextButton`, which declares it.</span></span> <span data-ttu-id="2195a-120">Un tipo speciale di proprietà di dipendenza è la proprietà di dipendenza collegata.</span><span class="sxs-lookup"><span data-stu-id="2195a-120">A special kind of dependency property is the attached dependency property.</span></span>  
  
 <span data-ttu-id="2195a-121">Un esempio classico di una proprietà associata è il <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> proprietà.</span><span class="sxs-lookup"><span data-stu-id="2195a-121">A classic example of an attached property is the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="2195a-122">La proprietà rappresenta la posizione di colonna del pulsante (non della griglia), ma rilevante solo se il pulsante è contenuto in una griglia, quindi è "connesso" a pulsanti da griglie.</span><span class="sxs-lookup"><span data-stu-id="2195a-122">The property represents Button’s (not Grid’s) column position, but it is only relevant if the Button is contained in a Grid, and so it's "attached" to Buttons by Grids.</span></span>  
  
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
  
 <span data-ttu-id="2195a-123">La definizione di una proprietà associata è simile principalmente a quello di una proprietà di dipendenza normale, ad eccezione del fatto che le funzioni di accesso sono rappresentati dai metodi Get e Set statici:</span><span class="sxs-lookup"><span data-stu-id="2195a-123">The definition of an attached property looks mostly like that of a regular dependency property, except that the accessors are represented by static Get and Set methods:</span></span>  
  
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
  
## <a name="dependency-property-validation"></a><span data-ttu-id="2195a-124">Convalida delle proprietà di dipendenza</span><span class="sxs-lookup"><span data-stu-id="2195a-124">Dependency Property Validation</span></span>  
 <span data-ttu-id="2195a-125">Proprietà implementano spesso cosiddetto convalida.</span><span class="sxs-lookup"><span data-stu-id="2195a-125">Properties often implement what is called validation.</span></span> <span data-ttu-id="2195a-126">La logica di convalida viene eseguita quando viene effettuato un tentativo di modificare il valore di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="2195a-126">Validation logic executes when an attempt is made to change the value of a property.</span></span>  
  
 <span data-ttu-id="2195a-127">Sfortunatamente accesso della proprietà di dipendenza non può contenere codice di convalida arbitraria.</span><span class="sxs-lookup"><span data-stu-id="2195a-127">Unfortunately dependency property accessors cannot contain arbitrary validation code.</span></span> <span data-ttu-id="2195a-128">Al contrario, logica di convalida di proprietà di dipendenza deve essere specificato durante la registrazione di proprietà.</span><span class="sxs-lookup"><span data-stu-id="2195a-128">Instead, dependency property validation logic needs to be specified during property registration.</span></span>  
  
 <span data-ttu-id="2195a-129">**X non** inserire logica di convalida di proprietà di dipendenza in funzioni di accesso della proprietà.</span><span class="sxs-lookup"><span data-stu-id="2195a-129">**X DO NOT** put dependency property validation logic in the property’s accessors.</span></span> <span data-ttu-id="2195a-130">Al contrario, passare un callback di convalida per `DependencyProperty.Register` metodo.</span><span class="sxs-lookup"><span data-stu-id="2195a-130">Instead, pass a validation callback to `DependencyProperty.Register` method.</span></span>  
  
## <a name="dependency-property-change-notifications"></a><span data-ttu-id="2195a-131">Notifiche di modifica proprietà di dipendenza</span><span class="sxs-lookup"><span data-stu-id="2195a-131">Dependency Property Change Notifications</span></span>  
 <span data-ttu-id="2195a-132">**X non** implementare la logica di notifica di modifica nell'accesso della proprietà di dipendenza.</span><span class="sxs-lookup"><span data-stu-id="2195a-132">**X DO NOT** implement change notification logic in dependency property accessors.</span></span> <span data-ttu-id="2195a-133">Le proprietà di dipendenza sono una funzionalità di notifiche di modifica incorporate che deve essere usata da fornire un callback di notifica di modifica per il <xref:System.Windows.PropertyMetadata>.</span><span class="sxs-lookup"><span data-stu-id="2195a-133">Dependency properties have a built-in change notifications feature that must be used by supplying a change notification callback to the <xref:System.Windows.PropertyMetadata>.</span></span>  
  
## <a name="dependency-property-value-coercion"></a><span data-ttu-id="2195a-134">Coercizione del valore di proprietà di dipendenza</span><span class="sxs-lookup"><span data-stu-id="2195a-134">Dependency Property Value Coercion</span></span>  
 <span data-ttu-id="2195a-135">Coercizione di proprietà ha luogo quando il valore in base a un setter di proprietà viene modificato dal setter prima che venga effettivamente modificata l'archivio delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="2195a-135">Property coercion takes place when the value given to a property setter is modified by the setter before the property store is actually modified.</span></span>  
  
 <span data-ttu-id="2195a-136">**X non** implementare la logica di coercizione nell'accesso della proprietà di dipendenza.</span><span class="sxs-lookup"><span data-stu-id="2195a-136">**X DO NOT** implement coercion logic in dependency property accessors.</span></span>  
  
 <span data-ttu-id="2195a-137">Le proprietà di dipendenza sono una funzionalità di coercizione incorporata e può essere utilizzato, fornendo un callback la coercizione di `PropertyMetadata`.</span><span class="sxs-lookup"><span data-stu-id="2195a-137">Dependency properties have a built-in coercion feature, and it can be used by supplying a coercion callback to the `PropertyMetadata`.</span></span>  
  
 <span data-ttu-id="2195a-138">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="2195a-138">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="2195a-139">*State ristampate dall'autorizzazione di Pearson Education, Inc. dal [Framework linee guida di progettazione: convenzioni, idiomi e modelli per le librerie .NET riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="2195a-139">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2195a-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2195a-140">See Also</span></span>  
 [<span data-ttu-id="2195a-141">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="2195a-141">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="2195a-142">Modelli di progettazione comuni</span><span class="sxs-lookup"><span data-stu-id="2195a-142">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)
