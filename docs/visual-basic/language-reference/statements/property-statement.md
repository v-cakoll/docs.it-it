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
ms.openlocfilehash: 21ca15d6a6939d884c7e6abedc1f7919be079edd
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43738146"
---
# <a name="property-statement"></a><span data-ttu-id="024f4-102">Property Statement</span><span class="sxs-lookup"><span data-stu-id="024f4-102">Property Statement</span></span>
<span data-ttu-id="024f4-103">Dichiara il nome di una proprietà e le routine della proprietà utilizzate per archiviare e recuperare il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="024f4-103">Declares the name of a property, and the property procedures used to store and retrieve the value of the property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="024f4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="024f4-104">Syntax</span></span>  
  
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
  
## <a name="parts"></a><span data-ttu-id="024f4-105">Parti</span><span class="sxs-lookup"><span data-stu-id="024f4-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="024f4-106">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="024f4-106">Optional.</span></span> <span data-ttu-id="024f4-107">Elenco di attributi che si applicano a questa proprietà o `Get` o `Set` procedure.</span><span class="sxs-lookup"><span data-stu-id="024f4-107">List of attributes that apply to this property or `Get` or `Set` procedure.</span></span> <span data-ttu-id="024f4-108">Visualizzare [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="024f4-108">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
-   `Default`  
  
     <span data-ttu-id="024f4-109">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="024f4-109">Optional.</span></span> <span data-ttu-id="024f4-110">Specifica che questa proprietà è la proprietà predefinita per la classe o struttura in cui è definito.</span><span class="sxs-lookup"><span data-stu-id="024f4-110">Specifies that this property is the default property for the class or structure on which it is defined.</span></span> <span data-ttu-id="024f4-111">Impostazione predefinita deve accettare parametri e possono essere impostare e recuperare proprietà senza specificare il nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="024f4-111">Default properties must accept parameters and can be set and retrieved without specifying the property name.</span></span> <span data-ttu-id="024f4-112">Se si dichiara la proprietà come `Default`, non è possibile usare `Private` sulla proprietà o in una delle routine della proprietà.</span><span class="sxs-lookup"><span data-stu-id="024f4-112">If you declare the property as `Default`, you cannot use `Private` on the property or on either of its property procedures.</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="024f4-113">Facoltativo nella `Property` istruzione e al massimo uno tra il `Get` e `Set` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="024f4-113">Optional on the `Property` statement and on at most one of the `Get` and `Set` statements.</span></span> <span data-ttu-id="024f4-114">Può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="024f4-114">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="024f4-115">Public</span><span class="sxs-lookup"><span data-stu-id="024f4-115">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="024f4-116">Protected</span><span class="sxs-lookup"><span data-stu-id="024f4-116">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="024f4-117">Friend</span><span class="sxs-lookup"><span data-stu-id="024f4-117">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="024f4-118">Private</span><span class="sxs-lookup"><span data-stu-id="024f4-118">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    - [<span data-ttu-id="024f4-119">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="024f4-119">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md) 

    - [<span data-ttu-id="024f4-120">Private Protected</span><span class="sxs-lookup"><span data-stu-id="024f4-120">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)
  
     <span data-ttu-id="024f4-121">Visualizzare [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="024f4-121">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `propertymodifiers`  
  
     <span data-ttu-id="024f4-122">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="024f4-122">Optional.</span></span> <span data-ttu-id="024f4-123">Può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="024f4-123">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="024f4-124">Overload</span><span class="sxs-lookup"><span data-stu-id="024f4-124">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [<span data-ttu-id="024f4-125">Overrides</span><span class="sxs-lookup"><span data-stu-id="024f4-125">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [<span data-ttu-id="024f4-126">Overridable</span><span class="sxs-lookup"><span data-stu-id="024f4-126">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [<span data-ttu-id="024f4-127">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="024f4-127">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="024f4-128">MustOverride</span><span class="sxs-lookup"><span data-stu-id="024f4-128">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="024f4-129">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="024f4-129">Optional.</span></span> <span data-ttu-id="024f4-130">Visualizzare [condiviso](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="024f4-130">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="024f4-131">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="024f4-131">Optional.</span></span> <span data-ttu-id="024f4-132">Visualizzare [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="024f4-132">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `ReadOnly`  
  
     <span data-ttu-id="024f4-133">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="024f4-133">Optional.</span></span> <span data-ttu-id="024f4-134">Visualizzare [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="024f4-134">See [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
-   `WriteOnly`  
  
     <span data-ttu-id="024f4-135">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="024f4-135">Optional.</span></span> <span data-ttu-id="024f4-136">Visualizzare [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).</span><span class="sxs-lookup"><span data-stu-id="024f4-136">See [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).</span></span>  
  
-   `Iterator`  
  
     <span data-ttu-id="024f4-137">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="024f4-137">Optional.</span></span> <span data-ttu-id="024f4-138">Visualizzare [iteratore](../../../visual-basic/language-reference/modifiers/iterator.md).</span><span class="sxs-lookup"><span data-stu-id="024f4-138">See [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="024f4-139">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="024f4-139">Required.</span></span> <span data-ttu-id="024f4-140">Nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="024f4-140">Name of the property.</span></span> <span data-ttu-id="024f4-141">Visualizzare [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="024f4-141">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="024f4-142">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="024f4-142">Optional.</span></span> <span data-ttu-id="024f4-143">Elenco di nomi delle variabili locali che rappresentano i parametri di questa proprietà e gli eventuali parametri aggiuntivi del `Set` procedure.</span><span class="sxs-lookup"><span data-stu-id="024f4-143">List of local variable names representing the parameters of this property, and possible additional parameters of the `Set` procedure.</span></span> <span data-ttu-id="024f4-144">Visualizzare [elenco di parametri](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="024f4-144">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>  
  
-   `returntype`  
  
     <span data-ttu-id="024f4-145">Obbligatorio se `Option Strict` è `On`.</span><span class="sxs-lookup"><span data-stu-id="024f4-145">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="024f4-146">Tipo di dati del valore restituito da questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="024f4-146">Data type of the value returned by this property.</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="024f4-147">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="024f4-147">Optional.</span></span> <span data-ttu-id="024f4-148">Indica che questa proprietà implementa una o più proprietà, ognuno dei quali definito in un'interfaccia implementata dalla classe o struttura contenente questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="024f4-148">Indicates that this property implements one or more properties, each one defined in an interface implemented by this property's containing class or structure.</span></span> <span data-ttu-id="024f4-149">Visualizzare [implementa istruzione](../../../visual-basic/language-reference/statements/implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="024f4-149">See [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="024f4-150">Necessario se si fornisce `Implements`.</span><span class="sxs-lookup"><span data-stu-id="024f4-150">Required if `Implements` is supplied.</span></span> <span data-ttu-id="024f4-151">Elenco di proprietà in fase di implementazione.</span><span class="sxs-lookup"><span data-stu-id="024f4-151">List of properties being implemented.</span></span>  
  
     `implementedproperty [ , implementedproperty ... ]`  
  
     <span data-ttu-id="024f4-152">Ogni `implementedproperty` presenta la sintassi e le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="024f4-152">Each `implementedproperty` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="024f4-153">Parte</span><span class="sxs-lookup"><span data-stu-id="024f4-153">Part</span></span>|<span data-ttu-id="024f4-154">Descrizione</span><span class="sxs-lookup"><span data-stu-id="024f4-154">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="024f4-155">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="024f4-155">Required.</span></span> <span data-ttu-id="024f4-156">Nome di un'interfaccia implementata da questa proprietà che contiene classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="024f4-156">Name of an interface implemented by this property's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="024f4-157">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="024f4-157">Required.</span></span> <span data-ttu-id="024f4-158">Nome mediante il quale la proprietà è definita in `interface`.</span><span class="sxs-lookup"><span data-stu-id="024f4-158">Name by which the property is defined in `interface`.</span></span>|  
  
-   `Get`  
  
     <span data-ttu-id="024f4-159">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="024f4-159">Optional.</span></span> <span data-ttu-id="024f4-160">Obbligatorio se la proprietà è contrassegnata `WriteOnly`.</span><span class="sxs-lookup"><span data-stu-id="024f4-160">Required if the property is marked `WriteOnly`.</span></span> <span data-ttu-id="024f4-161">Avvia un `Get` routine della proprietà che viene utilizzato per restituire il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="024f4-161">Starts a `Get` property procedure that is used to return the value of the property.</span></span>  
  
-   `statements`  
  
     <span data-ttu-id="024f4-162">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="024f4-162">Optional.</span></span> <span data-ttu-id="024f4-163">Blocco di istruzioni da eseguire all'interno di `Get` o `Set` procedure.</span><span class="sxs-lookup"><span data-stu-id="024f4-163">Block of statements to run within the `Get` or `Set` procedure.</span></span>  
  
-   `End Get`  
  
     <span data-ttu-id="024f4-164">Termina il `Get` routine della proprietà.</span><span class="sxs-lookup"><span data-stu-id="024f4-164">Terminates the `Get` property procedure.</span></span>  
  
-   `Set`  
  
     <span data-ttu-id="024f4-165">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="024f4-165">Optional.</span></span> <span data-ttu-id="024f4-166">Obbligatorio se la proprietà è contrassegnata `ReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="024f4-166">Required if the property is marked `ReadOnly`.</span></span> <span data-ttu-id="024f4-167">Avvia un `Set` routine della proprietà che viene usato per archiviare il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="024f4-167">Starts a `Set` property procedure that is used to store the value of the property.</span></span>  
  
-   `End Set`  
  
     <span data-ttu-id="024f4-168">Termina il `Set` routine della proprietà.</span><span class="sxs-lookup"><span data-stu-id="024f4-168">Terminates the `Set` property procedure.</span></span>  
  
-   `End Property`  
  
     <span data-ttu-id="024f4-169">Termina la definizione di questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="024f4-169">Terminates the definition of this property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="024f4-170">Note</span><span class="sxs-lookup"><span data-stu-id="024f4-170">Remarks</span></span>  
 <span data-ttu-id="024f4-171">Il `Property` istruzione introduce la dichiarazione di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="024f4-171">The `Property` statement introduces the declaration of a property.</span></span> <span data-ttu-id="024f4-172">Una proprietà può avere una `Get` procedure (sola lettura), un `Set` procedure (sola scrittura) o entrambe (lettura-scrittura).</span><span class="sxs-lookup"><span data-stu-id="024f4-172">A property can have a `Get` procedure (read only), a `Set` procedure (write only), or both (read-write).</span></span> <span data-ttu-id="024f4-173">È possibile omettere il `Get` e `Set` procedura quando si usa una proprietà implementata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="024f4-173">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="024f4-174">Per altre informazioni, vedere [Proprietà implementate automaticamente](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="024f4-174">For more information, see [Auto-Implemented Properties](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>  
  
 <span data-ttu-id="024f4-175">È possibile usare `Property` solo a livello di classe.</span><span class="sxs-lookup"><span data-stu-id="024f4-175">You can use `Property` only at class level.</span></span> <span data-ttu-id="024f4-176">Ciò significa che il *contesto della dichiarazione* per una proprietà deve essere una classe, struttura, modulo o interfaccia e non può essere un file di origine, lo spazio dei nomi, procedura o blocco.</span><span class="sxs-lookup"><span data-stu-id="024f4-176">This means the *declaration context* for a property must be a class, structure, module, or interface, and cannot be a source file, namespace, procedure, or block.</span></span> <span data-ttu-id="024f4-177">Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="024f4-177">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="024f4-178">Per impostazione predefinita, le proprietà usano l'accesso pubblico.</span><span class="sxs-lookup"><span data-stu-id="024f4-178">By default, properties use public access.</span></span> <span data-ttu-id="024f4-179">È possibile modificare il livello di accesso della proprietà con un modificatore di accesso nella `Property` istruzione ed è anche possibile impostare una delle routine della proprietà a un livello di accesso più restrittivo.</span><span class="sxs-lookup"><span data-stu-id="024f4-179">You can adjust a property's access level with an access modifier on the `Property` statement, and you can optionally adjust one of its property procedures to a more restrictive access level.</span></span>  
  
 <span data-ttu-id="024f4-180">Visual Basic passa un parametro per il `Set` procedura durante le assegnazioni di proprietà.</span><span class="sxs-lookup"><span data-stu-id="024f4-180">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="024f4-181">Se non si specifica un parametro per `Set`, l'ambiente di sviluppo integrato (IDE) usa un parametro implicito denominato `value`.</span><span class="sxs-lookup"><span data-stu-id="024f4-181">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="024f4-182">Questo parametro contiene il valore da assegnare alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="024f4-182">This parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="024f4-183">In genere archivia questo valore in una variabile locale privata e restituirlo ogni volta che il `Get` routine viene chiamata.</span><span class="sxs-lookup"><span data-stu-id="024f4-183">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="024f4-184">Regole</span><span class="sxs-lookup"><span data-stu-id="024f4-184">Rules</span></span>  
  
-   <span data-ttu-id="024f4-185">**Livelli di accesso misti.**</span><span class="sxs-lookup"><span data-stu-id="024f4-185">**Mixed Access Levels.**</span></span> <span data-ttu-id="024f4-186">Se si sta definendo una proprietà di lettura / scrittura, è possibile specificare facoltativamente un livello di accesso diversi per il `Get` o il `Set` procedure, ma non entrambi.</span><span class="sxs-lookup"><span data-stu-id="024f4-186">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="024f4-187">In questo caso, il livello di accesso di routine deve essere più restrittivo rispetto a livello di accesso della proprietà.</span><span class="sxs-lookup"><span data-stu-id="024f4-187">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="024f4-188">Ad esempio, se la proprietà è dichiarata `Friend`, è possibile dichiarare il `Set` routine `Private`, ma non `Public`.</span><span class="sxs-lookup"><span data-stu-id="024f4-188">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="024f4-189">Se si sta definendo un `ReadOnly` oppure `WriteOnly` proprietà, la procedura singola proprietà (`Get` o `Set`rispettivamente) rappresenta tutte le proprietà.</span><span class="sxs-lookup"><span data-stu-id="024f4-189">If you are defining a `ReadOnly` or `WriteOnly` property, the single property procedure (`Get` or `Set`, respectively) represents all of the property.</span></span> <span data-ttu-id="024f4-190">È possibile dichiarare un livello di accesso diversi per una procedura, poiché verrebbero specificati due livelli di accesso per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="024f4-190">You cannot declare a different access level for such a procedure, because that would set two access levels for the property.</span></span>  
  
-   <span data-ttu-id="024f4-191">**Tipo restituito.**</span><span class="sxs-lookup"><span data-stu-id="024f4-191">**Return Type.**</span></span> <span data-ttu-id="024f4-192">Il `Property` istruzione può dichiarare il tipo di dati del valore restituito.</span><span class="sxs-lookup"><span data-stu-id="024f4-192">The `Property` statement can declare the data type of the value it returns.</span></span> <span data-ttu-id="024f4-193">È possibile specificare qualsiasi tipo di dati o il nome di un'enumerazione, struttura, classe o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="024f4-193">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>  
  
     <span data-ttu-id="024f4-194">Se non si specifica `returntype`, la proprietà restituisce `Object`.</span><span class="sxs-lookup"><span data-stu-id="024f4-194">If you do not specify `returntype`, the property returns `Object`.</span></span>  
  
-   <span data-ttu-id="024f4-195">**Implementazione.**</span><span class="sxs-lookup"><span data-stu-id="024f4-195">**Implementation.**</span></span> <span data-ttu-id="024f4-196">Se questa proprietà Usa il `Implements` parola chiave, alla classe o struttura deve avere un' `Implements` istruzione immediatamente successiva a relativo `Class` o `Structure` istruzione.</span><span class="sxs-lookup"><span data-stu-id="024f4-196">If this property uses the `Implements` keyword, the containing class or structure must have an `Implements` statement immediately following its `Class` or `Structure` statement.</span></span> <span data-ttu-id="024f4-197">Il `Implements` istruzione deve includere ogni interfaccia specificata `implementslist`.</span><span class="sxs-lookup"><span data-stu-id="024f4-197">The `Implements` statement must include each interface specified in `implementslist`.</span></span> <span data-ttu-id="024f4-198">Tuttavia, il nome mediante il quale definisce un'interfaccia di `Property` (in `definedname`) non deve essere identico al nome di questa proprietà (in `name`).</span><span class="sxs-lookup"><span data-stu-id="024f4-198">However, the name by which an interface defines the `Property` (in `definedname`) does not have to be the same as the name of this property (in `name`).</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="024f4-199">Comportamento</span><span class="sxs-lookup"><span data-stu-id="024f4-199">Behavior</span></span>  
  
-   <span data-ttu-id="024f4-200">**Restituzione da una routine di proprietà.**</span><span class="sxs-lookup"><span data-stu-id="024f4-200">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="024f4-201">Quando la `Get` o `Set` routine restituisce al codice chiamante, l'esecuzione continua con l'istruzione successiva all'istruzione che lo ha richiamato.</span><span class="sxs-lookup"><span data-stu-id="024f4-201">When the `Get` or `Set` procedure returns to the calling code, execution continues with the statement following the statement that invoked it.</span></span>  
  
     <span data-ttu-id="024f4-202">Il `Exit Property` e `Return` istruzioni di uscire immediatamente da una routine di proprietà.</span><span class="sxs-lookup"><span data-stu-id="024f4-202">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="024f4-203">Un numero qualsiasi di `Exit Property` e `Return` istruzioni possono trovarsi in qualsiasi punto della procedura, ed è possibile combinare `Exit Property` e `Return` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="024f4-203">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
-   <span data-ttu-id="024f4-204">**Valore restituito.**</span><span class="sxs-lookup"><span data-stu-id="024f4-204">**Return Value.**</span></span> <span data-ttu-id="024f4-205">Per restituire un valore da un `Get` procedure, è possibile assegnare il valore per il nome della proprietà o includerlo in un `Return` istruzione.</span><span class="sxs-lookup"><span data-stu-id="024f4-205">To return a value from a `Get` procedure, you can either assign the value to the property name or include it in a `Return` statement.</span></span> <span data-ttu-id="024f4-206">L'esempio seguente assegna il valore restituito per il nome della proprietà `quoteForTheDay` e quindi Usa il `Exit Property` istruzione da restituire.</span><span class="sxs-lookup"><span data-stu-id="024f4-206">The following example assigns the return value to the property name `quoteForTheDay` and then uses the `Exit Property` statement to return.</span></span>  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#28](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_2.vb)]  
  
     <span data-ttu-id="024f4-207">Se si usa `Exit Property` senza assegnarle un valore per `name`, il `Get` procedure restituisce il valore predefinito per il tipo di dati della proprietà.</span><span class="sxs-lookup"><span data-stu-id="024f4-207">If you use `Exit Property` without assigning a value to `name`, the `Get` procedure returns the default value for the property's data type.</span></span>  
  
     <span data-ttu-id="024f4-208">Il `Return` istruzione allo stesso tempo assegna il `Get` procedure restituire valore e viene chiuso la procedura.</span><span class="sxs-lookup"><span data-stu-id="024f4-208">The `Return` statement at the same time assigns the `Get` procedure return value and exits the procedure.</span></span> <span data-ttu-id="024f4-209">L'esempio seguente illustra questo.</span><span class="sxs-lookup"><span data-stu-id="024f4-209">The following example shows this.</span></span>  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#29](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="024f4-210">Esempio</span><span class="sxs-lookup"><span data-stu-id="024f4-210">Example</span></span>  
 <span data-ttu-id="024f4-211">Nell'esempio seguente dichiara una proprietà in una classe.</span><span class="sxs-lookup"><span data-stu-id="024f4-211">The following example declares a property in a class.</span></span>  
  
 [!code-vb[VbVbalrStatements#51](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="024f4-212">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="024f4-212">See Also</span></span>  
 [<span data-ttu-id="024f4-213">Proprietà implementate automaticamente</span><span class="sxs-lookup"><span data-stu-id="024f4-213">Auto-Implemented Properties</span></span>](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)  
 [<span data-ttu-id="024f4-214">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="024f4-214">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="024f4-215">Istruzione Get</span><span class="sxs-lookup"><span data-stu-id="024f4-215">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)  
 [<span data-ttu-id="024f4-216">Istruzione Set</span><span class="sxs-lookup"><span data-stu-id="024f4-216">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)  
 [<span data-ttu-id="024f4-217">Elenco dei parametri</span><span class="sxs-lookup"><span data-stu-id="024f4-217">Parameter List</span></span>](../../../visual-basic/language-reference/statements/parameter-list.md)  
 [<span data-ttu-id="024f4-218">Default</span><span class="sxs-lookup"><span data-stu-id="024f4-218">Default</span></span>](../../../visual-basic/language-reference/modifiers/default.md)
