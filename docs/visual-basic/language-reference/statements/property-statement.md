---
title: Istruzione Property (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.PropertySet
- vb.Property
- vb.PropertyGet
helpviewer_keywords:
- Property statement [Visual Basic]
- default modifier
- property procedures [Visual Basic], Property statements
- Property keyword [Visual Basic]
ms.assetid: 3155edaf-8ebd-45c6-9cef-11d5d2dc8d38
ms.openlocfilehash: 2c3e417aad404171a43342dc92773615ec350ef5
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "71332739"
---
# <a name="property-statement"></a><span data-ttu-id="23a3d-102">Property Statement</span><span class="sxs-lookup"><span data-stu-id="23a3d-102">Property Statement</span></span>

<span data-ttu-id="23a3d-103">Dichiara il nome di una proprietà e le routine della proprietà usate per archiviare e recuperare il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="23a3d-103">Declares the name of a property, and the property procedures used to store and retrieve the value of the property.</span></span>

## <a name="syntax"></a><span data-ttu-id="23a3d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="23a3d-104">Syntax</span></span>

```vb
[ <attributelist> ] [ Default ] [ accessmodifier ]
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ] [ Iterator ]
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]
    [ <attributelist> ] [ accessmodifier ] Get
        [ statements ]
    End Get
    [ <attributelist> ] [ accessmodifier ] Set ( ByVal value As returntype [, parameterlist ] )
        [ statements ]
    End Set
End Property
- or -
[ <attributelist> ] [ Default ] [ accessmodifier ]
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ]
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]
```

## <a name="parts"></a><span data-ttu-id="23a3d-105">Parti</span><span class="sxs-lookup"><span data-stu-id="23a3d-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="23a3d-106">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="23a3d-106">Optional.</span></span> <span data-ttu-id="23a3d-107">Elenco degli attributi che si applicano a questa proprietà o alla procedura `Get` o `Set`.</span><span class="sxs-lookup"><span data-stu-id="23a3d-107">List of attributes that apply to this property or `Get` or `Set` procedure.</span></span> <span data-ttu-id="23a3d-108">Vedere [elenco attributi](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="23a3d-108">See [Attribute List](attribute-list.md).</span></span>

- `Default`

  <span data-ttu-id="23a3d-109">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="23a3d-109">Optional.</span></span> <span data-ttu-id="23a3d-110">Specifica che questa proprietà è la proprietà predefinita della classe o della struttura in cui è definita.</span><span class="sxs-lookup"><span data-stu-id="23a3d-110">Specifies that this property is the default property for the class or structure on which it is defined.</span></span> <span data-ttu-id="23a3d-111">Le proprietà predefinite devono accettare parametri e possono essere impostate e recuperate senza specificare il nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="23a3d-111">Default properties must accept parameters and can be set and retrieved without specifying the property name.</span></span> <span data-ttu-id="23a3d-112">Se si dichiara la proprietà come `Default`, non è possibile utilizzare `Private` sulla proprietà o su una delle relative routine di proprietà.</span><span class="sxs-lookup"><span data-stu-id="23a3d-112">If you declare the property as `Default`, you cannot use `Private` on the property or on either of its property procedures.</span></span>

- `accessmodifier`

  <span data-ttu-id="23a3d-113">Facoltativo nell'istruzione `Property` e al massimo una delle istruzioni `Get` e `Set`.</span><span class="sxs-lookup"><span data-stu-id="23a3d-113">Optional on the `Property` statement and on at most one of the `Get` and `Set` statements.</span></span> <span data-ttu-id="23a3d-114">Può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="23a3d-114">Can be one of the following:</span></span>

  - [<span data-ttu-id="23a3d-115">Public</span><span class="sxs-lookup"><span data-stu-id="23a3d-115">Public</span></span>](../modifiers/public.md)

  - [<span data-ttu-id="23a3d-116">Protected</span><span class="sxs-lookup"><span data-stu-id="23a3d-116">Protected</span></span>](../modifiers/protected.md)

  - [<span data-ttu-id="23a3d-117">Friend</span><span class="sxs-lookup"><span data-stu-id="23a3d-117">Friend</span></span>](../modifiers/friend.md)

  - [<span data-ttu-id="23a3d-118">Private</span><span class="sxs-lookup"><span data-stu-id="23a3d-118">Private</span></span>](../modifiers/private.md)

  - [<span data-ttu-id="23a3d-119">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="23a3d-119">Protected Friend</span></span>](../modifiers/protected-friend.md)

  - [<span data-ttu-id="23a3d-120">Private Protected</span><span class="sxs-lookup"><span data-stu-id="23a3d-120">Private Protected</span></span>](../modifiers/private-protected.md)

  <span data-ttu-id="23a3d-121">Vedere [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="23a3d-121">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `propertymodifiers`

  <span data-ttu-id="23a3d-122">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="23a3d-122">Optional.</span></span> <span data-ttu-id="23a3d-123">Può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="23a3d-123">Can be one of the following:</span></span>

  - [<span data-ttu-id="23a3d-124">Overload</span><span class="sxs-lookup"><span data-stu-id="23a3d-124">Overloads</span></span>](../modifiers/overloads.md)

  - [<span data-ttu-id="23a3d-125">Overrides</span><span class="sxs-lookup"><span data-stu-id="23a3d-125">Overrides</span></span>](../modifiers/overrides.md)

  - [<span data-ttu-id="23a3d-126">Overridable</span><span class="sxs-lookup"><span data-stu-id="23a3d-126">Overridable</span></span>](../modifiers/overridable.md)

  - [<span data-ttu-id="23a3d-127">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="23a3d-127">NotOverridable</span></span>](../modifiers/notoverridable.md)

  - [<span data-ttu-id="23a3d-128">MustOverride</span><span class="sxs-lookup"><span data-stu-id="23a3d-128">MustOverride</span></span>](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  <span data-ttu-id="23a3d-129">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="23a3d-129">Optional.</span></span> <span data-ttu-id="23a3d-130">Vedere [Shared](../modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="23a3d-130">See [Shared](../modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="23a3d-131">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="23a3d-131">Optional.</span></span> <span data-ttu-id="23a3d-132">Vedere [Shadows](../modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="23a3d-132">See [Shadows](../modifiers/shadows.md).</span></span>

- `ReadOnly`

  <span data-ttu-id="23a3d-133">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="23a3d-133">Optional.</span></span> <span data-ttu-id="23a3d-134">Vedere [ReadOnly](../modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="23a3d-134">See [ReadOnly](../modifiers/readonly.md).</span></span>

- `WriteOnly`

  <span data-ttu-id="23a3d-135">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="23a3d-135">Optional.</span></span> <span data-ttu-id="23a3d-136">Vedere [WriteOnly](../modifiers/writeonly.md).</span><span class="sxs-lookup"><span data-stu-id="23a3d-136">See [WriteOnly](../modifiers/writeonly.md).</span></span>

- `Iterator`

  <span data-ttu-id="23a3d-137">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="23a3d-137">Optional.</span></span> <span data-ttu-id="23a3d-138">Vedere [iteratore](../modifiers/iterator.md).</span><span class="sxs-lookup"><span data-stu-id="23a3d-138">See [Iterator](../modifiers/iterator.md).</span></span>

- `name`

  <span data-ttu-id="23a3d-139">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="23a3d-139">Required.</span></span> <span data-ttu-id="23a3d-140">Nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="23a3d-140">Name of the property.</span></span> <span data-ttu-id="23a3d-141">Vedere [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="23a3d-141">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

- `parameterlist`

  <span data-ttu-id="23a3d-142">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="23a3d-142">Optional.</span></span> <span data-ttu-id="23a3d-143">Elenco di nomi di variabili locali che rappresentano i parametri di questa proprietà e possibili parametri aggiuntivi della procedura `Set`.</span><span class="sxs-lookup"><span data-stu-id="23a3d-143">List of local variable names representing the parameters of this property, and possible additional parameters of the `Set` procedure.</span></span> <span data-ttu-id="23a3d-144">Vedere [elenco di parametri](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="23a3d-144">See [Parameter List](parameter-list.md).</span></span>

- `returntype`

  <span data-ttu-id="23a3d-145">Obbligatorio se `Option Strict` è `On`.</span><span class="sxs-lookup"><span data-stu-id="23a3d-145">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="23a3d-146">Tipo di dati del valore restituito da questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="23a3d-146">Data type of the value returned by this property.</span></span>

- `Implements`

  <span data-ttu-id="23a3d-147">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="23a3d-147">Optional.</span></span> <span data-ttu-id="23a3d-148">Indica che questa proprietà implementa una o più proprietà, ognuna delle quali è definita in un'interfaccia implementata dalla classe o dalla struttura contenitore di questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="23a3d-148">Indicates that this property implements one or more properties, each one defined in an interface implemented by this property's containing class or structure.</span></span> <span data-ttu-id="23a3d-149">Vedere [istruzione Implements](implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="23a3d-149">See [Implements Statement](implements-statement.md).</span></span>

- `implementslist`

  <span data-ttu-id="23a3d-150">Necessario se si fornisce `Implements`.</span><span class="sxs-lookup"><span data-stu-id="23a3d-150">Required if `Implements` is supplied.</span></span> <span data-ttu-id="23a3d-151">Elenco delle proprietà implementate.</span><span class="sxs-lookup"><span data-stu-id="23a3d-151">List of properties being implemented.</span></span>

  `implementedproperty [ , implementedproperty ... ]`

  <span data-ttu-id="23a3d-152">Ogni `implementedproperty` presenta la sintassi e le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="23a3d-152">Each `implementedproperty` has the following syntax and parts:</span></span>

  `interface.definedname`

  |<span data-ttu-id="23a3d-153">Parte</span><span class="sxs-lookup"><span data-stu-id="23a3d-153">Part</span></span>|<span data-ttu-id="23a3d-154">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23a3d-154">Description</span></span>|
  |---|---|
  |`interface`|<span data-ttu-id="23a3d-155">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="23a3d-155">Required.</span></span> <span data-ttu-id="23a3d-156">Nome di un'interfaccia implementata dalla classe o dalla struttura contenitore di questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="23a3d-156">Name of an interface implemented by this property's containing class or structure.</span></span>|
  |`definedname`|<span data-ttu-id="23a3d-157">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="23a3d-157">Required.</span></span> <span data-ttu-id="23a3d-158">Nome con cui viene definita la proprietà in `interface`.</span><span class="sxs-lookup"><span data-stu-id="23a3d-158">Name by which the property is defined in `interface`.</span></span>|

- `Get`

  <span data-ttu-id="23a3d-159">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="23a3d-159">Optional.</span></span> <span data-ttu-id="23a3d-160">Obbligatorio se la proprietà è contrassegnata `ReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="23a3d-160">Required if the property is marked `ReadOnly`.</span></span> <span data-ttu-id="23a3d-161">Avvia una routine della proprietà `Get` utilizzata per restituire il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="23a3d-161">Starts a `Get` property procedure that is used to return the value of the property.</span></span>  <span data-ttu-id="23a3d-162">L'istruzione `Get` non viene utilizzata con le [proprietà implementate automaticamente](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="23a3d-162">The `Get` statement is not used with [auto-implemented properties](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>

- `statements`

  <span data-ttu-id="23a3d-163">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="23a3d-163">Optional.</span></span> <span data-ttu-id="23a3d-164">Blocco di istruzioni da eseguire all'interno della procedura `Get` o `Set`.</span><span class="sxs-lookup"><span data-stu-id="23a3d-164">Block of statements to run within the `Get` or `Set` procedure.</span></span>

- `End Get`

  <span data-ttu-id="23a3d-165">Termina la routine della proprietà `Get`.</span><span class="sxs-lookup"><span data-stu-id="23a3d-165">Terminates the `Get` property procedure.</span></span>

- `Set`

  <span data-ttu-id="23a3d-166">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="23a3d-166">Optional.</span></span> <span data-ttu-id="23a3d-167">Obbligatorio se la proprietà è contrassegnata `WriteOnly`.</span><span class="sxs-lookup"><span data-stu-id="23a3d-167">Required if the property is marked `WriteOnly`.</span></span> <span data-ttu-id="23a3d-168">Avvia una routine della proprietà `Set` utilizzata per archiviare il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="23a3d-168">Starts a `Set` property procedure that is used to store the value of the property.</span></span>  <span data-ttu-id="23a3d-169">L'istruzione `Set` non viene utilizzata con le [proprietà implementate automaticamente](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="23a3d-169">The `Set` statement is not used with [auto-implemented properties](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>

- `End Set`

  <span data-ttu-id="23a3d-170">Termina la routine della proprietà `Set`.</span><span class="sxs-lookup"><span data-stu-id="23a3d-170">Terminates the `Set` property procedure.</span></span>

- `End Property`

  <span data-ttu-id="23a3d-171">Termina la definizione di questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="23a3d-171">Terminates the definition of this property.</span></span>

## <a name="remarks"></a><span data-ttu-id="23a3d-172">Note</span><span class="sxs-lookup"><span data-stu-id="23a3d-172">Remarks</span></span>

<span data-ttu-id="23a3d-173">L'istruzione `Property` introduce la dichiarazione di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="23a3d-173">The `Property` statement introduces the declaration of a property.</span></span> <span data-ttu-id="23a3d-174">Una proprietà può avere una routine `Get` (sola lettura), una procedura `Set` (sola scrittura) o entrambe (lettura/scrittura).</span><span class="sxs-lookup"><span data-stu-id="23a3d-174">A property can have a `Get` procedure (read only), a `Set` procedure (write only), or both (read-write).</span></span> <span data-ttu-id="23a3d-175">È possibile omettere la procedura `Get` e `Set` quando si usa una proprietà implementata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="23a3d-175">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="23a3d-176">Per altre informazioni, vedere [Proprietà implementate automaticamente](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="23a3d-176">For more information, see [Auto-Implemented Properties](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>

<span data-ttu-id="23a3d-177">È possibile utilizzare `Property` solo a livello di classe.</span><span class="sxs-lookup"><span data-stu-id="23a3d-177">You can use `Property` only at class level.</span></span> <span data-ttu-id="23a3d-178">Ciò significa che il *contesto di dichiarazione* per una proprietà deve essere una classe, una struttura, un modulo o un'interfaccia e non può essere un file di origine, uno spazio dei nomi, una procedura o un blocco.</span><span class="sxs-lookup"><span data-stu-id="23a3d-178">This means the *declaration context* for a property must be a class, structure, module, or interface, and cannot be a source file, namespace, procedure, or block.</span></span> <span data-ttu-id="23a3d-179">Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="23a3d-179">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="23a3d-180">Per impostazione predefinita, le proprietà usano l'accesso pubblico.</span><span class="sxs-lookup"><span data-stu-id="23a3d-180">By default, properties use public access.</span></span> <span data-ttu-id="23a3d-181">È possibile modificare il livello di accesso di una proprietà con un modificatore di accesso nell'istruzione `Property` ed è possibile modificare facoltativamente una delle routine di proprietà a un livello di accesso più restrittivo.</span><span class="sxs-lookup"><span data-stu-id="23a3d-181">You can adjust a property's access level with an access modifier on the `Property` statement, and you can optionally adjust one of its property procedures to a more restrictive access level.</span></span>

<span data-ttu-id="23a3d-182">Visual Basic passa un parametro alla procedura `Set` durante le assegnazioni di proprietà.</span><span class="sxs-lookup"><span data-stu-id="23a3d-182">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="23a3d-183">Se non si specifica un parametro per `Set`, il Integrated Development Environment (IDE) utilizza un parametro implicito denominato `value`.</span><span class="sxs-lookup"><span data-stu-id="23a3d-183">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="23a3d-184">Questo parametro include il valore da assegnare alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="23a3d-184">This parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="23a3d-185">Questo valore viene in genere archiviato in una variabile locale privata e restituito ogni volta che viene chiamata la procedura `Get`.</span><span class="sxs-lookup"><span data-stu-id="23a3d-185">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>

## <a name="rules"></a><span data-ttu-id="23a3d-186">Regole</span><span class="sxs-lookup"><span data-stu-id="23a3d-186">Rules</span></span>

- <span data-ttu-id="23a3d-187">**Livelli di accesso misti.**</span><span class="sxs-lookup"><span data-stu-id="23a3d-187">**Mixed Access Levels.**</span></span> <span data-ttu-id="23a3d-188">Se si definisce una proprietà di lettura/scrittura, è possibile specificare facoltativamente un livello di accesso diverso per la procedura `Get` o `Set`, ma non per entrambi.</span><span class="sxs-lookup"><span data-stu-id="23a3d-188">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="23a3d-189">In tal caso, il livello di accesso della routine deve essere più restrittivo del livello di accesso della proprietà.</span><span class="sxs-lookup"><span data-stu-id="23a3d-189">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="23a3d-190">Se, ad esempio, la proprietà è dichiarata `Friend`, è possibile dichiarare la procedura `Set` `Private`, ma non `Public`.</span><span class="sxs-lookup"><span data-stu-id="23a3d-190">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>

  <span data-ttu-id="23a3d-191">Se si definisce una proprietà `ReadOnly` o `WriteOnly`, la routine della proprietà singola (rispettivamente `Get` o `Set`) rappresenta tutta la proprietà.</span><span class="sxs-lookup"><span data-stu-id="23a3d-191">If you are defining a `ReadOnly` or `WriteOnly` property, the single property procedure (`Get` or `Set`, respectively) represents all of the property.</span></span> <span data-ttu-id="23a3d-192">Non è possibile dichiarare un livello di accesso diverso per una procedura di questo tipo, perché imposta due livelli di accesso per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="23a3d-192">You cannot declare a different access level for such a procedure, because that would set two access levels for the property.</span></span>

- <span data-ttu-id="23a3d-193">**Tipo restituito.**</span><span class="sxs-lookup"><span data-stu-id="23a3d-193">**Return Type.**</span></span> <span data-ttu-id="23a3d-194">L'istruzione `Property` può dichiarare il tipo di dati del valore restituito.</span><span class="sxs-lookup"><span data-stu-id="23a3d-194">The `Property` statement can declare the data type of the value it returns.</span></span> <span data-ttu-id="23a3d-195">È possibile specificare qualsiasi tipo di dati o il nome di un'enumerazione, una struttura, una classe o un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="23a3d-195">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>

  <span data-ttu-id="23a3d-196">Se non si specifica `returntype`, la proprietà restituisce `Object`.</span><span class="sxs-lookup"><span data-stu-id="23a3d-196">If you do not specify `returntype`, the property returns `Object`.</span></span>

- <span data-ttu-id="23a3d-197">**Implementazione.**</span><span class="sxs-lookup"><span data-stu-id="23a3d-197">**Implementation.**</span></span> <span data-ttu-id="23a3d-198">Se questa proprietà Usa la parola chiave `Implements`, la classe o la struttura contenitore deve avere un'istruzione `Implements` immediatamente dopo la relativa istruzione `Class` o `Structure`.</span><span class="sxs-lookup"><span data-stu-id="23a3d-198">If this property uses the `Implements` keyword, the containing class or structure must have an `Implements` statement immediately following its `Class` or `Structure` statement.</span></span> <span data-ttu-id="23a3d-199">L'istruzione `Implements` deve includere ogni interfaccia specificata in `implementslist`.</span><span class="sxs-lookup"><span data-stu-id="23a3d-199">The `Implements` statement must include each interface specified in `implementslist`.</span></span> <span data-ttu-id="23a3d-200">Tuttavia, il nome con cui un'interfaccia definisce il `Property` (in `definedname`) non deve corrispondere al nome di questa proprietà (in `name`).</span><span class="sxs-lookup"><span data-stu-id="23a3d-200">However, the name by which an interface defines the `Property` (in `definedname`) does not have to be the same as the name of this property (in `name`).</span></span>

## <a name="behavior"></a><span data-ttu-id="23a3d-201">Comportamento</span><span class="sxs-lookup"><span data-stu-id="23a3d-201">Behavior</span></span>

- <span data-ttu-id="23a3d-202">**Restituzione da una routine di proprietà.**</span><span class="sxs-lookup"><span data-stu-id="23a3d-202">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="23a3d-203">Quando la procedura `Get` o `Set` restituisce al codice chiamante, l'esecuzione continua con l'istruzione che segue l'istruzione che lo ha richiamato.</span><span class="sxs-lookup"><span data-stu-id="23a3d-203">When the `Get` or `Set` procedure returns to the calling code, execution continues with the statement following the statement that invoked it.</span></span>

  <span data-ttu-id="23a3d-204">Le istruzioni `Exit Property` e `Return` provocano una chiusura immediata da una routine Property.</span><span class="sxs-lookup"><span data-stu-id="23a3d-204">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="23a3d-205">Qualsiasi numero di istruzioni `Exit Property` e `Return` può comparire in qualsiasi punto della procedura ed è possibile combinare le istruzioni `Exit Property` e `Return`.</span><span class="sxs-lookup"><span data-stu-id="23a3d-205">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>

- <span data-ttu-id="23a3d-206">**Valore restituito.**</span><span class="sxs-lookup"><span data-stu-id="23a3d-206">**Return Value.**</span></span> <span data-ttu-id="23a3d-207">Per restituire un valore da una routine `Get`, è possibile assegnare il valore al nome della proprietà o includerlo in un'istruzione `Return`.</span><span class="sxs-lookup"><span data-stu-id="23a3d-207">To return a value from a `Get` procedure, you can either assign the value to the property name or include it in a `Return` statement.</span></span> <span data-ttu-id="23a3d-208">Nell'esempio seguente viene assegnato il valore restituito al nome della proprietà `quoteForTheDay`, quindi viene utilizzata l'istruzione `Exit Property` per restituire.</span><span class="sxs-lookup"><span data-stu-id="23a3d-208">The following example assigns the return value to the property name `quoteForTheDay` and then uses the `Exit Property` statement to return.</span></span>

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]

  <span data-ttu-id="23a3d-209">Se si usa `Exit Property` senza assegnare un valore a `name`, la procedura `Get` restituisce il valore predefinito per il tipo di dati della proprietà.</span><span class="sxs-lookup"><span data-stu-id="23a3d-209">If you use `Exit Property` without assigning a value to `name`, the `Get` procedure returns the default value for the property's data type.</span></span>

  <span data-ttu-id="23a3d-210">L'istruzione `Return`, allo stesso tempo, assegna il valore restituito della procedura `Get` e chiude la procedura.</span><span class="sxs-lookup"><span data-stu-id="23a3d-210">The `Return` statement at the same time assigns the `Get` procedure return value and exits the procedure.</span></span> <span data-ttu-id="23a3d-211">Nell'esempio seguente viene illustrato questo.</span><span class="sxs-lookup"><span data-stu-id="23a3d-211">The following example shows this.</span></span>

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]

## <a name="example"></a><span data-ttu-id="23a3d-212">Esempio</span><span class="sxs-lookup"><span data-stu-id="23a3d-212">Example</span></span>

<span data-ttu-id="23a3d-213">Nell'esempio seguente viene dichiarata una proprietà in una classe.</span><span class="sxs-lookup"><span data-stu-id="23a3d-213">The following example declares a property in a class.</span></span>

[!code-vb[VbVbalrStatements#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#51)]

## <a name="see-also"></a><span data-ttu-id="23a3d-214">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23a3d-214">See also</span></span>

- [<span data-ttu-id="23a3d-215">Proprietà implementate automaticamente</span><span class="sxs-lookup"><span data-stu-id="23a3d-215">Auto-Implemented Properties</span></span>](../../programming-guide/language-features/procedures/auto-implemented-properties.md)
- [<span data-ttu-id="23a3d-216">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="23a3d-216">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="23a3d-217">Istruzione Get</span><span class="sxs-lookup"><span data-stu-id="23a3d-217">Get Statement</span></span>](get-statement.md)
- [<span data-ttu-id="23a3d-218">Istruzione Set</span><span class="sxs-lookup"><span data-stu-id="23a3d-218">Set Statement</span></span>](set-statement.md)
- [<span data-ttu-id="23a3d-219">Elenco dei parametri</span><span class="sxs-lookup"><span data-stu-id="23a3d-219">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="23a3d-220">Default</span><span class="sxs-lookup"><span data-stu-id="23a3d-220">Default</span></span>](../modifiers/default.md)
