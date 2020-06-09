---
title: Oggetti e classi
ms.date: 05/26/2020
helpviewer_keywords:
- classes [Visual Basic]
- objects [Visual Basic]
ms.assetid: c68c5752-1006-46e1-975a-6717b62a42fc
ms.openlocfilehash: 9e3cf262ef617a1ae5ee92bcc3d6fd5c691602f9
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600413"
---
# <a name="objects-and-classes-in-visual-basic"></a><span data-ttu-id="3c928-102">Oggetti e classi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3c928-102">Objects and classes in Visual Basic</span></span>

<span data-ttu-id="3c928-103">Un *oggetto* è una combinazione di codice e dati che è possibile considerare come singola unità.</span><span class="sxs-lookup"><span data-stu-id="3c928-103">An *object* is a combination of code and data that can be treated as a unit.</span></span> <span data-ttu-id="3c928-104">Un oggetto può essere una parte di un'applicazione, ad esempio un controllo o un form.</span><span class="sxs-lookup"><span data-stu-id="3c928-104">An object can be a piece of an application, like a control or a form.</span></span> <span data-ttu-id="3c928-105">Anche un'intera applicazione può essere un oggetto.</span><span class="sxs-lookup"><span data-stu-id="3c928-105">An entire application can also be an object.</span></span>

<span data-ttu-id="3c928-106">Quando si crea un'applicazione in Visual Basic, si utilizzano costantemente gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="3c928-106">When you create an application in Visual Basic, you constantly work with objects.</span></span> <span data-ttu-id="3c928-107">È possibile utilizzare gli oggetti forniti da Visual Basic, ad esempio controlli, form e oggetti di accesso ai dati.</span><span class="sxs-lookup"><span data-stu-id="3c928-107">You can use objects provided by Visual Basic, such as controls, forms, and data access objects.</span></span> <span data-ttu-id="3c928-108">È anche possibile usare oggetti di altre applicazioni all'interno dell'applicazione Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3c928-108">You can also use objects from other applications within your Visual Basic application.</span></span> <span data-ttu-id="3c928-109">È inoltre possibile creare oggetti personalizzati e definire per essi proprietà e metodi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="3c928-109">You can even create your own objects and define additional properties and methods for them.</span></span> <span data-ttu-id="3c928-110">Per i programmi, gli oggetti svolgono la stessa funzione dei blocchi predefiniti. Consentono infatti di scrivere un pezzo di codice una sola volta e di riutilizzarlo quanto necessario.</span><span class="sxs-lookup"><span data-stu-id="3c928-110">Objects act like prefabricated building blocks for programs — they let you write a piece of code once and reuse it over and over.</span></span>

<span data-ttu-id="3c928-111">Questo argomento fornisce informazioni dettagliate sugli oggetti.</span><span class="sxs-lookup"><span data-stu-id="3c928-111">This topic discusses objects in detail.</span></span>

## <a name="objects-and-classes"></a><span data-ttu-id="3c928-112">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="3c928-112">Objects and classes</span></span>

<span data-ttu-id="3c928-113">Ogni oggetto in Visual Basic è definito da una *classe*.</span><span class="sxs-lookup"><span data-stu-id="3c928-113">Each object in Visual Basic is defined by a *class*.</span></span> <span data-ttu-id="3c928-114">che ne descrive le variabili, le proprietà, le routine e gli eventi.</span><span class="sxs-lookup"><span data-stu-id="3c928-114">A class describes the variables, properties, procedures, and events of an object.</span></span> <span data-ttu-id="3c928-115">Gli oggetti sono istanze di classi. Dopo aver definito una classe, sarà possibile creare tutti gli oggetti necessari.</span><span class="sxs-lookup"><span data-stu-id="3c928-115">Objects are instances of classes; you can create as many objects you need once you have defined a class.</span></span>

<span data-ttu-id="3c928-116">Per comprendere la relazione esistente tra un oggetto e la classe di appartenenza, si pensi alla relazione tra gli stampi per biscotti e i biscotti.</span><span class="sxs-lookup"><span data-stu-id="3c928-116">To understand the relationship between an object and its class, think of cookie cutters and cookies.</span></span> <span data-ttu-id="3c928-117">La classe è lo stampo</span><span class="sxs-lookup"><span data-stu-id="3c928-117">The cookie cutter is the class.</span></span> <span data-ttu-id="3c928-118">che definisce le caratteristiche di ogni biscotto, ad esempio le dimensioni e la forma.</span><span class="sxs-lookup"><span data-stu-id="3c928-118">It defines the characteristics of each cookie, for example size and shape.</span></span> <span data-ttu-id="3c928-119">La classe viene usata per creare oggetti.</span><span class="sxs-lookup"><span data-stu-id="3c928-119">The class is used to create objects.</span></span> <span data-ttu-id="3c928-120">Gli oggetti sono i biscotti.</span><span class="sxs-lookup"><span data-stu-id="3c928-120">The objects are the cookies.</span></span>

<span data-ttu-id="3c928-121">È necessario creare un oggetto prima di poter accedere ai relativi membri, ad eccezione dei [`Shared`](../../../language-reference/modifiers/shared.md) membri a cui è possibile accedere senza un oggetto della classe.</span><span class="sxs-lookup"><span data-stu-id="3c928-121">You must create an object before you can access its members, except for [`Shared`](../../../language-reference/modifiers/shared.md) members which can be accessed without an object of the class.</span></span>

### <a name="create-an-object-from-a-class"></a><span data-ttu-id="3c928-122">Creare un oggetto da una classe</span><span class="sxs-lookup"><span data-stu-id="3c928-122">Create an object from a class</span></span>

1. <span data-ttu-id="3c928-123">Determinare da quale classe si desidera creare un oggetto o definire una classe personalizzata.</span><span class="sxs-lookup"><span data-stu-id="3c928-123">Determine from which class you want to create an object, or define your own class.</span></span> <span data-ttu-id="3c928-124">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3c928-124">For example:</span></span>

   ```vb
   Public Class Customer
       Public Property AccountNumber As Integer
   End Class
   ```

2. <span data-ttu-id="3c928-125">Scrivere un'[istruzione Dim](../../../language-reference/statements/dim-statement.md) per creare una variabile a cui assegnare un'istanza di una classe.</span><span class="sxs-lookup"><span data-stu-id="3c928-125">Write a [Dim Statement](../../../language-reference/statements/dim-statement.md) to create a variable to which you can assign a class instance.</span></span> <span data-ttu-id="3c928-126">La variabile dovrebbe essere del tipo della classe desiderata.</span><span class="sxs-lookup"><span data-stu-id="3c928-126">The variable should be of the type of the desired class.</span></span>

   ```vb
   Dim nextCustomer As Customer
   ```

3. <span data-ttu-id="3c928-127">Aggiungere la parola chiave [New](../../../language-reference/operators/new-operator.md) per inizializzare la variabile su una nuova istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="3c928-127">Add the [New Operator](../../../language-reference/operators/new-operator.md) keyword to initialize the variable to a new instance of the class.</span></span>

   ```vb
   Dim nextCustomer As New Customer
   ```

4. <span data-ttu-id="3c928-128">È ora possibile accedere ai membri della classe mediante la variabile oggetto.</span><span class="sxs-lookup"><span data-stu-id="3c928-128">You can now access the members of the class through the object variable.</span></span>

   ```vb
   nextCustomer.AccountNumber = lastAccountNumber + 1
   ```

> [!NOTE]
> <span data-ttu-id="3c928-129">Quando possibile, è necessario dichiarare che la variabile appartiene al tipo classe a cui si vuole assegnarla.</span><span class="sxs-lookup"><span data-stu-id="3c928-129">Whenever possible, you should declare the variable to be of the class type you intend to assign to it.</span></span> <span data-ttu-id="3c928-130">Questa operazione è definita *associazione anticipata*.</span><span class="sxs-lookup"><span data-stu-id="3c928-130">This is called *early binding*.</span></span> <span data-ttu-id="3c928-131">Se il tipo di classe non è noto in fase di compilazione, è possibile richiamare l'*associazione tardiva* dichiarando che la variabile è del [tipo di dati Object](../../../language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="3c928-131">If you don't know the class type at compile time, you can invoke *late binding* by declaring the variable to be of the [Object Data Type](../../../language-reference/data-types/object-data-type.md).</span></span> <span data-ttu-id="3c928-132">Questo tipo di associazione, tuttavia, può determinare un rallentamento delle prestazioni e limitare l'accesso ai membri dell'oggetto in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3c928-132">However, late binding can make performance slower and limit access to the run-time object's members.</span></span> <span data-ttu-id="3c928-133">Per altre informazioni, vedere [Object Variable Declaration](../variables/object-variable-declaration.md) (Dichiarazione di variabili oggetto).</span><span class="sxs-lookup"><span data-stu-id="3c928-133">For more information, see [Object Variable Declaration](../variables/object-variable-declaration.md).</span></span>

### <a name="multiple-instances"></a><span data-ttu-id="3c928-134">Istanze multiple</span><span class="sxs-lookup"><span data-stu-id="3c928-134">Multiple instances</span></span>

<span data-ttu-id="3c928-135">Gli oggetti creati da una classe sono spesso identici.</span><span class="sxs-lookup"><span data-stu-id="3c928-135">Objects newly created from a class are often identical to each other.</span></span> <span data-ttu-id="3c928-136">Una volta definiti come singoli oggetti, è comunque possibile modificarne le variabili e le proprietà indipendentemente dalle altre istanze.</span><span class="sxs-lookup"><span data-stu-id="3c928-136">Once they exist as individual objects, however, their variables and properties can be changed independently of the other instances.</span></span> <span data-ttu-id="3c928-137">Se, ad esempio, si aggiungono tre caselle di controllo a un form, ogni oggetto casella di controllo è un'istanza della classe <xref:System.Windows.Forms.CheckBox>.</span><span class="sxs-lookup"><span data-stu-id="3c928-137">For example, if you add three check boxes to a form, each check box object is an instance of the <xref:System.Windows.Forms.CheckBox> class.</span></span> <span data-ttu-id="3c928-138">I singoli oggetti <xref:System.Windows.Forms.CheckBox> condividono un set di caratteristiche e funzionalità, ad esempio proprietà, variabili, routine ed eventi, definito dalla classe.</span><span class="sxs-lookup"><span data-stu-id="3c928-138">The individual <xref:System.Windows.Forms.CheckBox> objects share a common set of characteristics and capabilities (properties, variables, procedures, and events) defined by the class.</span></span> <span data-ttu-id="3c928-139">Ognuno di essi, tuttavia, ha un proprio nome, può essere abilitato e disabilitato separatamente e può essere posizionato in un punto diverso del form.</span><span class="sxs-lookup"><span data-stu-id="3c928-139">However, each has its own name, can be separately enabled and disabled, and can be placed in a different location on the form.</span></span>

## <a name="object-members"></a><span data-ttu-id="3c928-140">Membri di oggetti</span><span class="sxs-lookup"><span data-stu-id="3c928-140">Object members</span></span>

<span data-ttu-id="3c928-141">Un oggetto è un elemento di un'applicazione che rappresenta un'*istanza* di una classe.</span><span class="sxs-lookup"><span data-stu-id="3c928-141">An object is an element of an application, representing an *instance* of a class.</span></span> <span data-ttu-id="3c928-142">I campi, le proprietà, i metodi e gli eventi sono i blocchi predefiniti degli oggetti e ne costituiscono i *membri*.</span><span class="sxs-lookup"><span data-stu-id="3c928-142">Fields, properties, methods, and events are the building blocks of objects and constitute their *members*.</span></span>

### <a name="member-access"></a><span data-ttu-id="3c928-143">Accesso ai membri</span><span class="sxs-lookup"><span data-stu-id="3c928-143">Member Access</span></span>

<span data-ttu-id="3c928-144">Per accedere a un membro di un oggetto, è necessario specificare il nome della variabile oggetto, un punto (`.`) e il nome del membro, nell'ordine indicato.</span><span class="sxs-lookup"><span data-stu-id="3c928-144">You access a member of an object by specifying, in order, the name of the object variable, a period (`.`), and the name of the member.</span></span> <span data-ttu-id="3c928-145">Nell'esempio seguente viene impostata la proprietà <xref:System.Windows.Forms.Control.Text%2A> di un oggetto <xref:System.Windows.Forms.Label>.</span><span class="sxs-lookup"><span data-stu-id="3c928-145">The following example sets the <xref:System.Windows.Forms.Control.Text%2A> property of a <xref:System.Windows.Forms.Label> object.</span></span>

```vb
warningLabel.Text = "Data not saved"
```

#### <a name="intellisense-listing-of-members"></a><span data-ttu-id="3c928-146">Elenco di membri IntelliSense</span><span class="sxs-lookup"><span data-stu-id="3c928-146">IntelliSense listing of members</span></span>

<span data-ttu-id="3c928-147">Quando si richiama l'opzione Elenca membri relativa a una classe, ad esempio quando si digita un punto (`.`) come operatore di accesso ai membri, IntelliSense elenca i membri di tale classe.</span><span class="sxs-lookup"><span data-stu-id="3c928-147">IntelliSense lists members of a class when you invoke its List Members option, for example when you type a period (`.`) as a member-access operator.</span></span> <span data-ttu-id="3c928-148">Se si digita il punto dopo il nome di una variabile dichiarata come istanza della classe, vengono elencati tutti i membri di istanza ma nessuno dei membri condivisi.</span><span class="sxs-lookup"><span data-stu-id="3c928-148">If you type the period following the name of a variable declared as an instance of that class, IntelliSense lists all the instance members and none of the shared members.</span></span> <span data-ttu-id="3c928-149">Se si digita il punto dopo il nome della classe, vengono elencati tutti i membri condivisi ma nessuno dei membri di istanza.</span><span class="sxs-lookup"><span data-stu-id="3c928-149">If you type the period following the class name itself, IntelliSense lists all the shared members and none of the instance members.</span></span> <span data-ttu-id="3c928-150">Per altre informazioni, vedere [Using IntelliSense](/visualstudio/ide/using-intellisense) (Uso di IntelliSense).</span><span class="sxs-lookup"><span data-stu-id="3c928-150">For more information, see [Using IntelliSense](/visualstudio/ide/using-intellisense).</span></span>

### <a name="fields-and-properties"></a><span data-ttu-id="3c928-151">Campi e proprietà</span><span class="sxs-lookup"><span data-stu-id="3c928-151">Fields and properties</span></span>

<span data-ttu-id="3c928-152">I *campi* e le *proprietà* rappresentano le informazioni contenute in un oggetto.</span><span class="sxs-lookup"><span data-stu-id="3c928-152">*Fields* and *properties* represent information stored in an object.</span></span> <span data-ttu-id="3c928-153">È possibile recuperare e impostare i valori dei campi e delle proprietà usando le istruzioni di assegnazione, nello stesso modo in cui si recuperano e impostano le variabili locali di una routine.</span><span class="sxs-lookup"><span data-stu-id="3c928-153">You retrieve and set their values with assignment statements the same way you retrieve and set local variables in a procedure.</span></span> <span data-ttu-id="3c928-154">Nell'esempio seguente viene recuperata la proprietà <xref:System.Windows.Forms.Control.Width%2A> e impostata la proprietà <xref:System.Windows.Forms.Control.ForeColor%2A> di un oggetto <xref:System.Windows.Forms.Label>.</span><span class="sxs-lookup"><span data-stu-id="3c928-154">The following example retrieves the <xref:System.Windows.Forms.Control.Width%2A> property and sets the <xref:System.Windows.Forms.Control.ForeColor%2A> property of a <xref:System.Windows.Forms.Label> object.</span></span>

```vb
Dim warningWidth As Integer = warningLabel.Width
warningLabel.ForeColor = System.Drawing.Color.Red
```

<span data-ttu-id="3c928-155">Si noti che un campo viene chiamato anche *variabile membro*.</span><span class="sxs-lookup"><span data-stu-id="3c928-155">Note that a field is also called a *member variable*.</span></span>

<span data-ttu-id="3c928-156">Usare le routine delle proprietà nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3c928-156">Use property procedures when:</span></span>

- <span data-ttu-id="3c928-157">È necessario controllare come e quando un valore viene impostato o recuperato.</span><span class="sxs-lookup"><span data-stu-id="3c928-157">You need to control when and how a value is set or retrieved.</span></span>

- <span data-ttu-id="3c928-158">La proprietà presenta un insieme di valori ben definito che è necessario convalidare.</span><span class="sxs-lookup"><span data-stu-id="3c928-158">The property has a well-defined set of values that need to be validated.</span></span>

- <span data-ttu-id="3c928-159">L'impostazione di un valore determina modifiche percettibili nello stato dell'oggetto, ad esempio una proprietà `IsVisible`.</span><span class="sxs-lookup"><span data-stu-id="3c928-159">Setting the value causes some perceptible change in the object's state, such as an `IsVisible` property.</span></span>

- <span data-ttu-id="3c928-160">L'impostazione della proprietà determina modifiche ad altre variabili interne o ai valori di altre proprietà.</span><span class="sxs-lookup"><span data-stu-id="3c928-160">Setting the property causes changes to other internal variables or to the values of other properties.</span></span>

- <span data-ttu-id="3c928-161">Per poter impostare o recuperare la proprietà, è necessario eseguire prima una serie di passaggi.</span><span class="sxs-lookup"><span data-stu-id="3c928-161">A set of steps must be performed before the property can be set or retrieved.</span></span>

<span data-ttu-id="3c928-162">Usare i campi nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3c928-162">Use fields when:</span></span>

- <span data-ttu-id="3c928-163">Il valore è di tipo auto-convalidante.</span><span class="sxs-lookup"><span data-stu-id="3c928-163">The value is of a self-validating type.</span></span> <span data-ttu-id="3c928-164">Ad esempio, se a una variabile `Boolean` viene assegnato un valore diverso da `True` o `False`, si verifica un errore o una conversione automatica di dati.</span><span class="sxs-lookup"><span data-stu-id="3c928-164">For example, an error or automatic data conversion occurs if a value other than `True` or `False` is assigned to a `Boolean` variable.</span></span>

- <span data-ttu-id="3c928-165">Tutti i valori compresi nell'intervallo supportato dal tipo dati sono validi.</span><span class="sxs-lookup"><span data-stu-id="3c928-165">Any value in the range supported by the data type is valid.</span></span> <span data-ttu-id="3c928-166">Questa affermazione è vera per diverse proprietà di tipo `Single` o `Double`.</span><span class="sxs-lookup"><span data-stu-id="3c928-166">This is true of many properties of type `Single` or `Double`.</span></span>

- <span data-ttu-id="3c928-167">La proprietà è un tipo dati `String`. Non è presente alcun vincolo riguardo alle dimensioni o al valore della stringa.</span><span class="sxs-lookup"><span data-stu-id="3c928-167">The property is a `String` data type, and there is no constraint on the size or value of the string.</span></span>

- <span data-ttu-id="3c928-168">Per altre informazioni, vedere [Routine Property](../procedures/property-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="3c928-168">For more information, see [Property Procedures](../procedures/property-procedures.md).</span></span>

> [!TIP]
> <span data-ttu-id="3c928-169">Mantieni sempre i campi non costanti privati.</span><span class="sxs-lookup"><span data-stu-id="3c928-169">Always keep the non-constant fields private.</span></span> <span data-ttu-id="3c928-170">Quando si desidera renderla pubblica, utilizzare invece una proprietà.</span><span class="sxs-lookup"><span data-stu-id="3c928-170">When you want to make it public, use a property instead.</span></span>

### <a name="methods"></a><span data-ttu-id="3c928-171">Metodi</span><span class="sxs-lookup"><span data-stu-id="3c928-171">Methods</span></span>

<span data-ttu-id="3c928-172">Un *metodo* è un'azione che può essere eseguita da un oggetto.</span><span class="sxs-lookup"><span data-stu-id="3c928-172">A *method* is an action that an object can perform.</span></span> <span data-ttu-id="3c928-173">Ad esempio, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Add%2A> è un metodo dell'oggetto <xref:System.Windows.Forms.ComboBox> che aggiunge una nuova voce in una casella combinata.</span><span class="sxs-lookup"><span data-stu-id="3c928-173">For example, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Add%2A> is a method of the <xref:System.Windows.Forms.ComboBox> object that adds a new entry to a combo box.</span></span>

<span data-ttu-id="3c928-174">Nell'esempio seguente viene illustrato il metodo <xref:System.Windows.Forms.Timer.Start%2A> di un oggetto <xref:System.Windows.Forms.Timer>.</span><span class="sxs-lookup"><span data-stu-id="3c928-174">The following example demonstrates the <xref:System.Windows.Forms.Timer.Start%2A> method of a <xref:System.Windows.Forms.Timer> object.</span></span>

```vb
Dim safetyTimer As New System.Windows.Forms.Timer
safetyTimer.Start()
```

<span data-ttu-id="3c928-175">Si noti che un metodo è semplicemente una *routine* esposta da un oggetto.</span><span class="sxs-lookup"><span data-stu-id="3c928-175">Note that a method is simply a *procedure* that is exposed by an object.</span></span>

<span data-ttu-id="3c928-176">Per altre informazioni, vedere [Routine](../procedures/index.md).</span><span class="sxs-lookup"><span data-stu-id="3c928-176">For more information, see [Procedures](../procedures/index.md).</span></span>

### <a name="events"></a><span data-ttu-id="3c928-177">Eventi</span><span class="sxs-lookup"><span data-stu-id="3c928-177">Events</span></span>

<span data-ttu-id="3c928-178">Un evento è un'azione che viene riconosciuta da un oggetto, ad esempio il clic del mouse o la pressione di un tasto, e alla quale è possibile rispondere mediante un codice scritto appositamente.</span><span class="sxs-lookup"><span data-stu-id="3c928-178">An event is an action recognized by an object, such as clicking the mouse or pressing a key, and for which you can write code to respond.</span></span> <span data-ttu-id="3c928-179">Gli eventi possono verificarsi come conseguenza di un'azione utente o un codice programma oppure possono essere generati dal sistema.</span><span class="sxs-lookup"><span data-stu-id="3c928-179">Events can occur as a result of a user action or program code, or they can be caused by the system.</span></span> <span data-ttu-id="3c928-180">Il codice che segnala un evento è detto codice che *genera* l'evento, mentre il codice che risponde all'evento è detto codice che *gestisce* l'evento.</span><span class="sxs-lookup"><span data-stu-id="3c928-180">Code that signals an event is said to *raise* the event, and code that responds to it is said to *handle* it.</span></span>

<span data-ttu-id="3c928-181">È inoltre possibile sviluppare eventi personalizzati generati dai propri oggetti e gestiti da altri oggetti.</span><span class="sxs-lookup"><span data-stu-id="3c928-181">You can also develop your own custom events to be raised by your objects and handled by other objects.</span></span> <span data-ttu-id="3c928-182">Per altre informazioni, vedere [Eventi](../events/index.md).</span><span class="sxs-lookup"><span data-stu-id="3c928-182">For more information, see [Events](../events/index.md).</span></span>

### <a name="instance-members-and-shared-members"></a><span data-ttu-id="3c928-183">Membri di istanza e membri condivisi</span><span class="sxs-lookup"><span data-stu-id="3c928-183">Instance members and shared members</span></span>

<span data-ttu-id="3c928-184">Quando si crea un oggetto da una classe, il risultato è un'istanza di tale classe.</span><span class="sxs-lookup"><span data-stu-id="3c928-184">When you create an object from a class, the result is an instance of that class.</span></span> <span data-ttu-id="3c928-185">I membri non dichiarati con la parola chiave [Shared](../../../language-reference/modifiers/shared.md) sono *membri di istanza* e appartengono soltanto a tale istanza.</span><span class="sxs-lookup"><span data-stu-id="3c928-185">Members that are not declared with the [Shared](../../../language-reference/modifiers/shared.md) keyword are *instance members*, which belong strictly to that particular instance.</span></span> <span data-ttu-id="3c928-186">Un membro di istanza appartenente a una determinata istanza è indipendente dallo stesso membro appartenente a un'altra istanza della stessa classe.</span><span class="sxs-lookup"><span data-stu-id="3c928-186">An instance member in one instance is independent of the same member in another instance of the same class.</span></span> <span data-ttu-id="3c928-187">Una variabile membro di istanza, ad esempio, può avere valori differenti in istanze differenti.</span><span class="sxs-lookup"><span data-stu-id="3c928-187">An instance member variable, for example, can have different values in different instances.</span></span>

<span data-ttu-id="3c928-188">I membri dichiarati con la parola chiave `Shared` sono *membri condivisi*. Questo significa che appartengono all'intera classe e non a una particolare istanza.</span><span class="sxs-lookup"><span data-stu-id="3c928-188">Members declared with the `Shared` keyword are *shared members*, which belong to the class as a whole and not to any particular instance.</span></span> <span data-ttu-id="3c928-189">Un membro condiviso viene definito una sola volta, indipendentemente dal numero di istanze della relativa classe che vengono create. Questo è vero anche se non viene creata alcuna istanza.</span><span class="sxs-lookup"><span data-stu-id="3c928-189">A shared member exists only once, no matter how many instances of its class you create, or even if you create no instances.</span></span> <span data-ttu-id="3c928-190">Una variabile membro condiviso, ad esempio, può avere un unico valore, che può essere usato da tutto il codice che ha accesso alla classe.</span><span class="sxs-lookup"><span data-stu-id="3c928-190">A shared member variable, for example, has only one value, which is available to all code that can access the class.</span></span>

#### <a name="accessing-non-shared-members"></a><span data-ttu-id="3c928-191">Accesso a membri non condivisi</span><span class="sxs-lookup"><span data-stu-id="3c928-191">Accessing non-shared members</span></span>

1. <span data-ttu-id="3c928-192">Verificare che l'oggetto sia stato creato a partire dalla relativa classe e che sia stato assegnato a una variabile oggetto.</span><span class="sxs-lookup"><span data-stu-id="3c928-192">Make sure the object has been created from its class and assigned to an object variable.</span></span>

   ```vb
   Dim secondForm As New System.Windows.Forms.Form
   ```

2. <span data-ttu-id="3c928-193">Nell'istruzione che accede al membro, seguire il nome della variabile oggetto con l' *operatore di accesso ai membri* ( `.` ) e quindi il nome del membro.</span><span class="sxs-lookup"><span data-stu-id="3c928-193">In the statement that accesses the member, follow the object variable name with the *member-access operator* (`.`) and then the member name.</span></span>

   ```vb
   secondForm.Show()
   ```

#### <a name="accessing-shared-members"></a><span data-ttu-id="3c928-194">Accesso a membri condivisi</span><span class="sxs-lookup"><span data-stu-id="3c928-194">Accessing shared members</span></span>

- <span data-ttu-id="3c928-195">Seguire il nome della classe con l' *operatore di accesso ai membri* ( `.` ) e quindi il nome del membro.</span><span class="sxs-lookup"><span data-stu-id="3c928-195">Follow the class name with the *member-access operator* (`.`) and then the member name.</span></span> <span data-ttu-id="3c928-196">È necessario accedere sempre a un membro `Shared` dell'oggetto tramite il nome della classe.</span><span class="sxs-lookup"><span data-stu-id="3c928-196">You should always access a `Shared` member of the object directly through the class name.</span></span>

   ```vb
   Console.WriteLine("This computer is called " & Environment.MachineName)
   ```

- <span data-ttu-id="3c928-197">In alternativa, se è già stato creato un oggetto a partire dalla classe, è possibile accedere a un membro `Shared` tramite la variabile dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="3c928-197">If you have already created an object from the class, you can alternatively access a `Shared` member through the object's variable.</span></span>

### <a name="differences-between-classes-and-modules"></a><span data-ttu-id="3c928-198">Differenze tra classi e moduli</span><span class="sxs-lookup"><span data-stu-id="3c928-198">Differences between classes and modules</span></span>

<span data-ttu-id="3c928-199">La differenza principale tra le classi e i moduli consiste nel fatto che è possibile creare istanze delle classi come oggetti, ma tale operazione non è possibile per i moduli standard.</span><span class="sxs-lookup"><span data-stu-id="3c928-199">The main difference between classes and modules is that classes can be instantiated as objects while standard modules cannot.</span></span> <span data-ttu-id="3c928-200">Poiché è presente una sola copia di dati di un modulo standard, quando una parte del programma modifica una variabile pubblica in un modulo standard, a una successiva lettura della variabile qualsiasi altra parte del programma ottiene lo stesso valore.</span><span class="sxs-lookup"><span data-stu-id="3c928-200">Because there is only one copy of a standard module's data, when one part of your program changes a public variable in a standard module, any other part of the program gets the same value if it then reads that variable.</span></span> <span data-ttu-id="3c928-201">I dati oggetto, invece, sono separati per ciascun oggetto di cui è stata creata un'istanza.</span><span class="sxs-lookup"><span data-stu-id="3c928-201">In contrast, object data exists separately for each instantiated object.</span></span> <span data-ttu-id="3c928-202">A differenza dei moduli standard, inoltre, le classi possono implementare interfacce.</span><span class="sxs-lookup"><span data-stu-id="3c928-202">Another difference is that unlike standard modules, classes can implement interfaces.</span></span> <span data-ttu-id="3c928-203">Se una classe è contrassegnata con il modificatore [MustInherit](../../../language-reference/modifiers/mustinherit.md) , non è possibile crearne un'istanza direttamente.</span><span class="sxs-lookup"><span data-stu-id="3c928-203">If a class is marked with the [MustInherit](../../../language-reference/modifiers/mustinherit.md) modifier, it can't be instantiated directly.</span></span> <span data-ttu-id="3c928-204">Tuttavia, è ancora diverso da un modulo perché può essere ereditato mentre i moduli non possono essere ereditati.</span><span class="sxs-lookup"><span data-stu-id="3c928-204">However, it's still different from a module as it can be inherited while modules can't be inherited.</span></span>

> [!NOTE]
> <span data-ttu-id="3c928-205">Quando si applica un modificatore `Shared` a un membro di una classe, il modificatore viene associato alla classe stessa anziché a una particolare istanza di quest'ultima.</span><span class="sxs-lookup"><span data-stu-id="3c928-205">When the `Shared` modifier is applied to a class member, it is associated with the class itself instead of a particular instance of the class.</span></span> <span data-ttu-id="3c928-206">L'accesso al membro avviene direttamente tramite il nome della classe, nello stesso modo in cui si accede ai membri del modulo.</span><span class="sxs-lookup"><span data-stu-id="3c928-206">The member is accessed directly by using the class name, the same way module members are accessed.</span></span>

<span data-ttu-id="3c928-207">Le classi e i moduli usano inoltre ambiti diversi per i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="3c928-207">Classes and modules also use different scopes for their members.</span></span> <span data-ttu-id="3c928-208">I membri definiti di una classe vengono dichiarati nell'ambito di una specifica istanza di tale classe ed esistono solo per la durata dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="3c928-208">Members defined within a class are scoped within a specific instance of the class and exist only for the lifetime of the object.</span></span> <span data-ttu-id="3c928-209">Per accedere ai membri di una classe dall'esterno di quest'ultima, è necessario usare nomi completi nel formato *Oggetto*.*Membro*.</span><span class="sxs-lookup"><span data-stu-id="3c928-209">To access class members from outside a class, you must use fully qualified names in the format of *Object*.*Member*.</span></span>

<span data-ttu-id="3c928-210">D'altra parte, i membri dichiarati all'interno di un modulo sono accessibili pubblicamente per impostazione predefinita e ad essi può accedere qualsiasi codice che abbia accesso al modulo.</span><span class="sxs-lookup"><span data-stu-id="3c928-210">On the other hand, members declared within a module are publicly accessible by default, and can be accessed by any code that can access the module.</span></span> <span data-ttu-id="3c928-211">Questo significa che le variabili presenti in un modulo standard sono effettivamente variabili globali poiché sono visibili da qualsiasi punto del progetto ed esistono per la durata del programma.</span><span class="sxs-lookup"><span data-stu-id="3c928-211">This means that variables in a standard module are effectively global variables because they are visible from anywhere in your project, and they exist for the life of the program.</span></span>

## <a name="reusing-classes-and-objects"></a><span data-ttu-id="3c928-212">Riutilizzo di classi e oggetti</span><span class="sxs-lookup"><span data-stu-id="3c928-212">Reusing classes and objects</span></span>

<span data-ttu-id="3c928-213">Grazie agli oggetti, è possibile dichiarare variabili e routine una sola volta e quindi riutilizzarle quando necessario.</span><span class="sxs-lookup"><span data-stu-id="3c928-213">Objects let you declare variables and procedures once and then reuse them whenever needed.</span></span> <span data-ttu-id="3c928-214">Se, ad esempio, si desidera aggiungere un correttore ortografico a un'applicazione, è possibile definire tutte le variabili e le funzioni di supporto per fornire la funzionalità di correttore ortografico.</span><span class="sxs-lookup"><span data-stu-id="3c928-214">For example, if you want to add a spelling checker to an application you could define all the variables and support functions to provide spell-checking functionality.</span></span> <span data-ttu-id="3c928-215">Se il controllo ortografico viene creato come classe, sarà possibile riutilizzarlo in altre applicazioni aggiungendo un riferimento all'assembly compilato.</span><span class="sxs-lookup"><span data-stu-id="3c928-215">If you create your spelling checker as a class, you can then reuse it in other applications by adding a reference to the compiled assembly.</span></span> <span data-ttu-id="3c928-216">Soluzione ancora migliore, sarà possibile risparmiare lavoro usando una classe correttore ortografico già sviluppata da altri programmatori.</span><span class="sxs-lookup"><span data-stu-id="3c928-216">Better yet, you may be able to save yourself some work by using a spelling checker class that someone else has already developed.</span></span>

<span data-ttu-id="3c928-217">.NET fornisce molti esempi di componenti disponibili per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="3c928-217">.NET provides many examples of components that are available for use.</span></span> <span data-ttu-id="3c928-218">Nell'esempio seguente viene usata la classe <xref:System.TimeZone> nello spazio dei nomi <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="3c928-218">The following example uses the <xref:System.TimeZone> class in the <xref:System> namespace.</span></span> <span data-ttu-id="3c928-219">La classe <xref:System.TimeZone> specifica i membri che consentono di recuperare le informazioni sul fuso orario del computer corrente.</span><span class="sxs-lookup"><span data-stu-id="3c928-219"><xref:System.TimeZone> provides members that allow you to retrieve information about the time zone of the current computer system.</span></span>

```vb
Public Sub ExamineTimeZone()
    Dim tz As System.TimeZone = System.TimeZone.CurrentTimeZone
    Dim s As String = "Current time zone is "
    s &= CStr(tz.GetUtcOffset(Now).Hours) & " hours and "
    s &= CStr(tz.GetUtcOffset(Now).Minutes) & " minutes "
    s &= "different from UTC (coordinated universal time)"
    s &= vbCrLf & "and is currently "
    If tz.IsDaylightSavingTime(Now) = False Then s &= "not "
    s &= "on ""summer time""."
    Console.WriteLine(s)
End Sub
```

<span data-ttu-id="3c928-220">Nell'esempio precedente, la prima [istruzione Dim](../../../language-reference/statements/dim-statement.md) dichiara una variabile oggetto di tipo <xref:System.TimeZone> e assegna alla variabile un oggetto <xref:System.TimeZone> restituito dalla proprietà <xref:System.TimeZone.CurrentTimeZone%2A>.</span><span class="sxs-lookup"><span data-stu-id="3c928-220">In the preceding example, the first [Dim Statement](../../../language-reference/statements/dim-statement.md) declares an object variable of type <xref:System.TimeZone> and assigns to it a <xref:System.TimeZone> object returned by the <xref:System.TimeZone.CurrentTimeZone%2A> property.</span></span>

## <a name="relationships-among-objects"></a><span data-ttu-id="3c928-221">Relazioni tra oggetti</span><span class="sxs-lookup"><span data-stu-id="3c928-221">Relationships among objects</span></span>

<span data-ttu-id="3c928-222">Gli oggetti possono essere posti in relazione tra loro in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="3c928-222">Objects can be related to each other in several ways.</span></span> <span data-ttu-id="3c928-223">Esistono due tipi principali di relazione, ovvero *gerarchica* e *di contenimento*.</span><span class="sxs-lookup"><span data-stu-id="3c928-223">The principal kinds of relationship are *hierarchical* and *containment*.</span></span>

### <a name="hierarchical-relationship"></a><span data-ttu-id="3c928-224">Relazione gerarchica</span><span class="sxs-lookup"><span data-stu-id="3c928-224">Hierarchical relationship</span></span>

<span data-ttu-id="3c928-225">Se sono presenti classi di maggiore importanza e classi da esse derivate, tra le prime e le seconde esiste una *relazione gerarchica*.</span><span class="sxs-lookup"><span data-stu-id="3c928-225">When classes are derived from more fundamental classes, they are said to have a *hierarchical relationship*.</span></span> <span data-ttu-id="3c928-226">Le gerarchie di classi sono utili per descrivere gli elementi che sono un sottotipo di una classe più generale.</span><span class="sxs-lookup"><span data-stu-id="3c928-226">Class hierarchies are useful when describing items that are a subtype of a more general class.</span></span>

<span data-ttu-id="3c928-227">Nell'esempio seguente, si supponga di voler definire un tipo speciale di classe <xref:System.Windows.Forms.Button> che si comporti come una classe <xref:System.Windows.Forms.Button> normale ma che allo stesso tempo esponga un metodo per invertire i colori di sfondo e di primo piano.</span><span class="sxs-lookup"><span data-stu-id="3c928-227">In the following example, suppose you want to define a special kind of <xref:System.Windows.Forms.Button> that acts like a normal <xref:System.Windows.Forms.Button> but also exposes a method that reverses the foreground and background colors.</span></span>

#### <a name="define-a-class-that-is-derived-from-an-already-existing-class"></a><span data-ttu-id="3c928-228">Definire una classe derivata da una classe già esistente</span><span class="sxs-lookup"><span data-stu-id="3c928-228">Define a class that is derived from an already existing class</span></span>

1. <span data-ttu-id="3c928-229">Usare un'[istruzione Class](../../../language-reference/statements/class-statement.md) per definire una classe dalla quale creare l'oggetto necessario.</span><span class="sxs-lookup"><span data-stu-id="3c928-229">Use a [Class Statement](../../../language-reference/statements/class-statement.md) to define a class from which to create the object you need.</span></span>

   ```vb
   Public Class ReversibleButton
   ```

   <span data-ttu-id="3c928-230">Verificare che l'ultima riga di codice della classe sia seguita da un'istruzione `End Class`.</span><span class="sxs-lookup"><span data-stu-id="3c928-230">Be sure an `End Class` statement follows the last line of code in your class.</span></span> <span data-ttu-id="3c928-231">Per impostazione predefinita, quando si immette un'istruzione `Class` l'ambiente di sviluppo integrato (IDE) genera automaticamente un'istruzione `End Class`.</span><span class="sxs-lookup"><span data-stu-id="3c928-231">By default, the integrated development environment (IDE) automatically generates an `End Class` when you enter a `Class` statement.</span></span>

2. <span data-ttu-id="3c928-232">Aggiungere un'[istruzione Inherits](../../../language-reference/statements/inherits-statement.md) subito dopo l'istruzione `Class`.</span><span class="sxs-lookup"><span data-stu-id="3c928-232">Follow the `Class` statement immediately with an [Inherits Statement](../../../language-reference/statements/inherits-statement.md).</span></span> <span data-ttu-id="3c928-233">Specificare la classe dalla quale deriva la nuova classe.</span><span class="sxs-lookup"><span data-stu-id="3c928-233">Specify the class from which your new class derives.</span></span>

   ```vb
   Inherits System.Windows.Forms.Button
   ```

   <span data-ttu-id="3c928-234">La nuova classe eredita tutti i membri definiti dalla classe di base.</span><span class="sxs-lookup"><span data-stu-id="3c928-234">Your new class inherits all the members defined by the base class.</span></span>

3. <span data-ttu-id="3c928-235">Aggiungere il codice per i membri aggiuntivi esposti dalla classe derivata.</span><span class="sxs-lookup"><span data-stu-id="3c928-235">Add the code for the additional members your derived class exposes.</span></span> <span data-ttu-id="3c928-236">Ad esempio, è possibile aggiungere un metodo `ReverseColors`. La classe derivata sarà simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="3c928-236">For example, you might add a `ReverseColors` method, and your derived class might look as follows:</span></span>

   ```vb
   Public Class ReversibleButton
       Inherits System.Windows.Forms.Button
           Public Sub ReverseColors()
               Dim saveColor As System.Drawing.Color = Me.BackColor
               Me.BackColor = Me.ForeColor
               Me.ForeColor = saveColor
          End Sub
   End Class
   ```

   <span data-ttu-id="3c928-237">Se si crea un oggetto dalla `ReversibleButton` classe, può accedere a tutti i membri della <xref:System.Windows.Forms.Button> classe, nonché al `ReverseColors` metodo e a qualsiasi altro nuovo membro definito in `ReversibleButton` .</span><span class="sxs-lookup"><span data-stu-id="3c928-237">If you create an object from the `ReversibleButton` class, it can access all the members of the <xref:System.Windows.Forms.Button> class, as well as the `ReverseColors` method and any other new members you define in `ReversibleButton`.</span></span>

<span data-ttu-id="3c928-238">Le classi derivate ereditano i membri della classe su cui sono basate, consentendo di raggiungere una maggiore complessità mano a mano che si avanza nella gerarchia.</span><span class="sxs-lookup"><span data-stu-id="3c928-238">Derived classes inherit members from the class they are based on, allowing you to add complexity as you progress in a class hierarchy.</span></span> <span data-ttu-id="3c928-239">Per altre informazioni, vedere [Nozioni fondamentali sull'ereditarietà](inheritance-basics.md).</span><span class="sxs-lookup"><span data-stu-id="3c928-239">For more information, see [Inheritance Basics](inheritance-basics.md).</span></span>

### <a name="compile-the-code"></a><span data-ttu-id="3c928-240">Compilare il codice</span><span class="sxs-lookup"><span data-stu-id="3c928-240">Compile the code</span></span>

<span data-ttu-id="3c928-241">Verificare che il compilatore possa accedere alla classe da cui si vuole derivare la nuova classe.</span><span class="sxs-lookup"><span data-stu-id="3c928-241">Be sure the compiler can access the class from which you intend to derive your new class.</span></span> <span data-ttu-id="3c928-242">A tale scopo è possibile fornire il nome completo della classe, come nell'esempio precedente, oppure specificare il relativo spazio dei nomi in un'[istruzione Imports (tipo e spazio dei nomi .NET)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="3c928-242">This might mean fully qualifying its name, as in the preceding example, or identifying its namespace in an [Imports Statement (.NET Namespace and Type)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span> <span data-ttu-id="3c928-243">Se la classe si trova in un progetto differente, può essere necessario aggiungere un riferimento a tale progetto.</span><span class="sxs-lookup"><span data-stu-id="3c928-243">If the class is in a different project, you might need to add a reference to that project.</span></span> <span data-ttu-id="3c928-244">Per ulteriori informazioni, vedere [gestione dei riferimenti in un progetto](/visualstudio/ide/managing-references-in-a-project).</span><span class="sxs-lookup"><span data-stu-id="3c928-244">For more information, see [Managing references in a project](/visualstudio/ide/managing-references-in-a-project).</span></span>

### <a name="containment-relationship"></a><span data-ttu-id="3c928-245">Relazione di contenuto</span><span class="sxs-lookup"><span data-stu-id="3c928-245">Containment relationship</span></span>

<span data-ttu-id="3c928-246">Un altro tipo di relazione tra oggetti è la *relazione di contenimento*.</span><span class="sxs-lookup"><span data-stu-id="3c928-246">Another way that objects can be related is a *containment relationship*.</span></span> <span data-ttu-id="3c928-247">Gli oggetti contenitore incapsulano logicamente altri oggetti.</span><span class="sxs-lookup"><span data-stu-id="3c928-247">Container objects logically encapsulate other objects.</span></span> <span data-ttu-id="3c928-248">Ad esempio, l'oggetto <xref:System.OperatingSystem> contiene logicamente un oggetto <xref:System.Version>, restituito tramite la proprietà <xref:System.OperatingSystem.Version%2A>.</span><span class="sxs-lookup"><span data-stu-id="3c928-248">For example, the <xref:System.OperatingSystem> object logically contains a <xref:System.Version> object, which it returns through its <xref:System.OperatingSystem.Version%2A> property.</span></span> <span data-ttu-id="3c928-249">Tenere presente che l'oggetto contenitore non contiene fisicamente altri oggetti.</span><span class="sxs-lookup"><span data-stu-id="3c928-249">Note that the container object does not physically contain any other object.</span></span>

#### <a name="collections"></a><span data-ttu-id="3c928-250">Raccolte</span><span class="sxs-lookup"><span data-stu-id="3c928-250">Collections</span></span>

<span data-ttu-id="3c928-251">Un tipo particolare di contenimento degli oggetti è rappresentato dalle *raccolte*.</span><span class="sxs-lookup"><span data-stu-id="3c928-251">One particular type of object containment is represented by *collections*.</span></span> <span data-ttu-id="3c928-252">Le raccolte sono gruppi di oggetti simili che possono essere enumerati.</span><span class="sxs-lookup"><span data-stu-id="3c928-252">Collections are groups of similar objects that can be enumerated.</span></span> <span data-ttu-id="3c928-253">Visual Basic supporta una sintassi specifica in [for each... Istruzione successiva](../../../language-reference/statements/for-each-next-statement.md) che consente di scorrere gli elementi di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="3c928-253">Visual Basic supports a specific syntax in the [For Each...Next Statement](../../../language-reference/statements/for-each-next-statement.md) that allows you to iterate through the items of a collection.</span></span> <span data-ttu-id="3c928-254">Inoltre, le raccolte consentono spesso di usare un <xref:Microsoft.VisualBasic.Collection.Item%2A> per recuperare gli elementi in base al relativo indice o tramite l'associazione a una stringa univoca.</span><span class="sxs-lookup"><span data-stu-id="3c928-254">Additionally, collections often allow you to use an <xref:Microsoft.VisualBasic.Collection.Item%2A> to retrieve elements by their index or by associating them with a unique string.</span></span> <span data-ttu-id="3c928-255">Le raccolte possono risultare di uso più semplice rispetto alle matrici, in quanto consentono di aggiungere o rimuovere elementi senza ricorrere agli indici.</span><span class="sxs-lookup"><span data-stu-id="3c928-255">Collections can be easier to use than arrays because they allow you to add or remove items without using indexes.</span></span> <span data-ttu-id="3c928-256">Grazie alla loro facilità d'uso, vengono spesso usate per l'archiviazione di form e controlli.</span><span class="sxs-lookup"><span data-stu-id="3c928-256">Because of their ease of use, collections are often used to store forms and controls.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3c928-257">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="3c928-257">Related topics</span></span>

<span data-ttu-id="3c928-258">[Procedura dettagliata: definizione delle classi](walkthrough-defining-classes.md)</span><span class="sxs-lookup"><span data-stu-id="3c928-258">[Walkthrough: Defining Classes](walkthrough-defining-classes.md)</span></span>\
<span data-ttu-id="3c928-259">Viene fornita una descrizione dettagliata della creazione di una classe.</span><span class="sxs-lookup"><span data-stu-id="3c928-259">Provides a step-by-step description of how to create a class.</span></span>

<span data-ttu-id="3c928-260">[Metodi e proprietà di overload](overloaded-properties-and-methods.md)</span><span class="sxs-lookup"><span data-stu-id="3c928-260">[Overloaded Properties and Methods](overloaded-properties-and-methods.md)</span></span>\
<span data-ttu-id="3c928-261">Metodi e proprietà di overload</span><span class="sxs-lookup"><span data-stu-id="3c928-261">Overloaded Properties and Methods</span></span>

<span data-ttu-id="3c928-262">[Nozioni fondamentali sull'ereditarietà](inheritance-basics.md)</span><span class="sxs-lookup"><span data-stu-id="3c928-262">[Inheritance Basics](inheritance-basics.md)</span></span>\
<span data-ttu-id="3c928-263">Vengono illustrati modificatori di ereditarietà, override di metodi e proprietà, MyClass e MyBase.</span><span class="sxs-lookup"><span data-stu-id="3c928-263">Covers inheritance modifiers, overriding methods and properties, MyClass, and MyBase.</span></span>

<span data-ttu-id="3c928-264">[Durata degli oggetti: come creare ed eliminare definitivamente oggetti](object-lifetime-how-objects-are-created-and-destroyed.md)</span><span class="sxs-lookup"><span data-stu-id="3c928-264">[Object Lifetime: How Objects Are Created and Destroyed](object-lifetime-how-objects-are-created-and-destroyed.md)</span></span>\
<span data-ttu-id="3c928-265">Vengono illustrate la creazione e l'eliminazione delle istanze di classe.</span><span class="sxs-lookup"><span data-stu-id="3c928-265">Discusses creating and disposing of class instances.</span></span>

<span data-ttu-id="3c928-266">[Tipi anonimi](anonymous-types.md)</span><span class="sxs-lookup"><span data-stu-id="3c928-266">[Anonymous Types](anonymous-types.md)</span></span>\
<span data-ttu-id="3c928-267">Viene descritto come creare e usare i tipi anonimi, che consentono di creare oggetti senza scrivere una definizione della classe per il tipo dati.</span><span class="sxs-lookup"><span data-stu-id="3c928-267">Describes how to create and use anonymous types, which allow you to create objects without writing a class definition for the data type.</span></span>

<span data-ttu-id="3c928-268">[Inizializzatori di oggetto: tipi denominati e anonimi](object-initializers-named-and-anonymous-types.md)</span><span class="sxs-lookup"><span data-stu-id="3c928-268">[Object Initializers: Named and Anonymous Types](object-initializers-named-and-anonymous-types.md)</span></span>\
<span data-ttu-id="3c928-269">Vengono discussi gli inizializzatori di oggetto, usati per creare istanze di tipi denominati e anonimi mediante un'unica espressione.</span><span class="sxs-lookup"><span data-stu-id="3c928-269">Discusses object initializers, which are used to create instances of named and anonymous types by using a single expression.</span></span>

<span data-ttu-id="3c928-270">[Procedura: dedurre tipi e nomi di proprietà nelle dichiarazioni di tipo anonimo](how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)</span><span class="sxs-lookup"><span data-stu-id="3c928-270">[How to: Infer Property Names and Types in Anonymous Type Declarations](how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)</span></span>\
<span data-ttu-id="3c928-271">Viene descritto come dedurre nomi e tipi di proprietà nelle dichiarazioni di tipo anonimo.</span><span class="sxs-lookup"><span data-stu-id="3c928-271">Explains how to infer property names and types in anonymous type declarations.</span></span> <span data-ttu-id="3c928-272">Vengono forniti esempi di inferenze riuscite e non riuscite.</span><span class="sxs-lookup"><span data-stu-id="3c928-272">Provides examples of successful and unsuccessful inference.</span></span>
