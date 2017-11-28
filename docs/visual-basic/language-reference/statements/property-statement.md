---
title: Property Statement
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "41"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: af4666ecb059f141480be2295055644537819293
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="property-statement"></a><span data-ttu-id="d3385-102">Property Statement</span><span class="sxs-lookup"><span data-stu-id="d3385-102">Property Statement</span></span>
<span data-ttu-id="d3385-103">Dichiara il nome di una proprietà e le routine della proprietà utilizzate per archiviare e recuperare il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d3385-103">Declares the name of a property, and the property procedures used to store and retrieve the value of the property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3385-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d3385-104">Syntax</span></span>  
  
```  
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
  
## <a name="parts"></a><span data-ttu-id="d3385-105">Parti</span><span class="sxs-lookup"><span data-stu-id="d3385-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="d3385-106">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d3385-106">Optional.</span></span> <span data-ttu-id="d3385-107">Elenco di attributi che si applicano a questa proprietà o `Get` o `Set` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="d3385-107">List of attributes that apply to this property or `Get` or `Set` procedure.</span></span> <span data-ttu-id="d3385-108">Vedere [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="d3385-108">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
-   `Default`  
  
     <span data-ttu-id="d3385-109">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d3385-109">Optional.</span></span> <span data-ttu-id="d3385-110">Specifica che questa proprietà è la proprietà predefinita per la classe o struttura in cui è definito.</span><span class="sxs-lookup"><span data-stu-id="d3385-110">Specifies that this property is the default property for the class or structure on which it is defined.</span></span> <span data-ttu-id="d3385-111">Le proprietà predefinite deve accettare parametri e possono essere impostate e recuperate senza specificare il nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d3385-111">Default properties must accept parameters and can be set and retrieved without specifying the property name.</span></span> <span data-ttu-id="d3385-112">Se si dichiara la proprietà come `Default`, non è possibile utilizzare `Private` sulla proprietà né sulle routine della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d3385-112">If you declare the property as `Default`, you cannot use `Private` on the property or on either of its property procedures.</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="d3385-113">Facoltativo per il `Property` istruzione e su almeno una del `Get` e `Set` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="d3385-113">Optional on the `Property` statement and on at most one of the `Get` and `Set` statements.</span></span> <span data-ttu-id="d3385-114">Può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="d3385-114">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="d3385-115">Public</span><span class="sxs-lookup"><span data-stu-id="d3385-115">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="d3385-116">Protected</span><span class="sxs-lookup"><span data-stu-id="d3385-116">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="d3385-117">Friend</span><span class="sxs-lookup"><span data-stu-id="d3385-117">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="d3385-118">Private</span><span class="sxs-lookup"><span data-stu-id="d3385-118">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     <span data-ttu-id="d3385-119">Vedere [accedere livelli in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="d3385-119">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `propertymodifiers`  
  
     <span data-ttu-id="d3385-120">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d3385-120">Optional.</span></span> <span data-ttu-id="d3385-121">Può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="d3385-121">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="d3385-122">Overload</span><span class="sxs-lookup"><span data-stu-id="d3385-122">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [<span data-ttu-id="d3385-123">Overrides</span><span class="sxs-lookup"><span data-stu-id="d3385-123">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [<span data-ttu-id="d3385-124">Overridable</span><span class="sxs-lookup"><span data-stu-id="d3385-124">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [<span data-ttu-id="d3385-125">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="d3385-125">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="d3385-126">MustOverride</span><span class="sxs-lookup"><span data-stu-id="d3385-126">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="d3385-127">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d3385-127">Optional.</span></span> <span data-ttu-id="d3385-128">Vedere [condiviso](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="d3385-128">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="d3385-129">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d3385-129">Optional.</span></span> <span data-ttu-id="d3385-130">Vedere [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="d3385-130">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `ReadOnly`  
  
     <span data-ttu-id="d3385-131">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d3385-131">Optional.</span></span> <span data-ttu-id="d3385-132">Vedere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="d3385-132">See [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
-   `WriteOnly`  
  
     <span data-ttu-id="d3385-133">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d3385-133">Optional.</span></span> <span data-ttu-id="d3385-134">Vedere [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).</span><span class="sxs-lookup"><span data-stu-id="d3385-134">See [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).</span></span>  
  
-   `Iterator`  
  
     <span data-ttu-id="d3385-135">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d3385-135">Optional.</span></span> <span data-ttu-id="d3385-136">Vedere [iteratore](../../../visual-basic/language-reference/modifiers/iterator.md).</span><span class="sxs-lookup"><span data-stu-id="d3385-136">See [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="d3385-137">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d3385-137">Required.</span></span> <span data-ttu-id="d3385-138">Nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d3385-138">Name of the property.</span></span> <span data-ttu-id="d3385-139">Vedere [nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="d3385-139">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="d3385-140">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d3385-140">Optional.</span></span> <span data-ttu-id="d3385-141">Elenco di nomi di variabili locali che rappresenta i parametri di questa proprietà e gli eventuali parametri aggiuntivi del `Set` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="d3385-141">List of local variable names representing the parameters of this property, and possible additional parameters of the `Set` procedure.</span></span> <span data-ttu-id="d3385-142">Vedere [elenco parametri](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="d3385-142">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>  
  
-   `returntype`  
  
     <span data-ttu-id="d3385-143">Obbligatorio se `Option``Strict` è `On`.</span><span class="sxs-lookup"><span data-stu-id="d3385-143">Required if `Option``Strict` is `On`.</span></span> <span data-ttu-id="d3385-144">Tipo di dati del valore restituito da questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="d3385-144">Data type of the value returned by this property.</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="d3385-145">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d3385-145">Optional.</span></span> <span data-ttu-id="d3385-146">Indica che questa proprietà implementa una o più proprietà, ciascuno definito in un'interfaccia implementata dalla classe o struttura che contiene questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="d3385-146">Indicates that this property implements one or more properties, each one defined in an interface implemented by this property's containing class or structure.</span></span> <span data-ttu-id="d3385-147">Vedere [implementa istruzione](../../../visual-basic/language-reference/statements/implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d3385-147">See [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="d3385-148">Necessario se si fornisce `Implements`.</span><span class="sxs-lookup"><span data-stu-id="d3385-148">Required if `Implements` is supplied.</span></span> <span data-ttu-id="d3385-149">Elenco di proprietà in fase di implementazione.</span><span class="sxs-lookup"><span data-stu-id="d3385-149">List of properties being implemented.</span></span>  
  
     `implementedproperty [ , implementedproperty ... ]`  
  
     <span data-ttu-id="d3385-150">Ogni `implementedproperty` presenta la sintassi e le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d3385-150">Each `implementedproperty` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="d3385-151">Parte</span><span class="sxs-lookup"><span data-stu-id="d3385-151">Part</span></span>|<span data-ttu-id="d3385-152">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d3385-152">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="d3385-153">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d3385-153">Required.</span></span> <span data-ttu-id="d3385-154">Nome di un'interfaccia implementata da questa proprietà contenente classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="d3385-154">Name of an interface implemented by this property's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="d3385-155">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d3385-155">Required.</span></span> <span data-ttu-id="d3385-156">Nome con cui la proprietà è definita in `interface`.</span><span class="sxs-lookup"><span data-stu-id="d3385-156">Name by which the property is defined in `interface`.</span></span>|  
  
-   `Get`  
  
     <span data-ttu-id="d3385-157">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d3385-157">Optional.</span></span> <span data-ttu-id="d3385-158">Obbligatorio se la proprietà è contrassegnata `WriteOnly`.</span><span class="sxs-lookup"><span data-stu-id="d3385-158">Required if the property is marked `WriteOnly`.</span></span> <span data-ttu-id="d3385-159">Avvia un `Get` routine di proprietà viene utilizzata per restituire il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d3385-159">Starts a `Get` property procedure that is used to return the value of the property.</span></span>  
  
-   `statements`  
  
     <span data-ttu-id="d3385-160">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d3385-160">Optional.</span></span> <span data-ttu-id="d3385-161">Blocco di istruzioni da eseguire all'interno di `Get` o `Set` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="d3385-161">Block of statements to run within the `Get` or `Set` procedure.</span></span>  
  
-   `End Get`  
  
     <span data-ttu-id="d3385-162">Termina il `Get` routine della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d3385-162">Terminates the `Get` property procedure.</span></span>  
  
-   `Set`  
  
     <span data-ttu-id="d3385-163">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d3385-163">Optional.</span></span> <span data-ttu-id="d3385-164">Obbligatorio se la proprietà è contrassegnata `ReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="d3385-164">Required if the property is marked `ReadOnly`.</span></span> <span data-ttu-id="d3385-165">Avvia un `Set` routine della proprietà utilizzato per archiviare il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d3385-165">Starts a `Set` property procedure that is used to store the value of the property.</span></span>  
  
-   `End Set`  
  
     <span data-ttu-id="d3385-166">Termina il `Set` routine della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d3385-166">Terminates the `Set` property procedure.</span></span>  
  
-   `End Property`  
  
     <span data-ttu-id="d3385-167">Termina la definizione di questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="d3385-167">Terminates the definition of this property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3385-168">Note</span><span class="sxs-lookup"><span data-stu-id="d3385-168">Remarks</span></span>  
 <span data-ttu-id="d3385-169">Il `Property` istruzione introduce la dichiarazione di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="d3385-169">The `Property` statement introduces the declaration of a property.</span></span> <span data-ttu-id="d3385-170">Una proprietà può avere un `Get` procedure (sola lettura), un `Set` procedure (sola scrittura) o entrambe (lettura-scrittura).</span><span class="sxs-lookup"><span data-stu-id="d3385-170">A property can have a `Get` procedure (read only), a `Set` procedure (write only), or both (read-write).</span></span> <span data-ttu-id="d3385-171">È possibile omettere il `Get` e `Set` procedura quando si usa una proprietà implementata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d3385-171">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="d3385-172">Per altre informazioni, vedere [Proprietà implementate automaticamente](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="d3385-172">For more information, see [Auto-Implemented Properties](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>  
  
 <span data-ttu-id="d3385-173">È possibile utilizzare `Property` solo a livello di classe.</span><span class="sxs-lookup"><span data-stu-id="d3385-173">You can use `Property` only at class level.</span></span> <span data-ttu-id="d3385-174">Ciò significa che il *contesto della dichiarazione* per una proprietà deve essere una classe, struttura, modulo o interfaccia e non può essere un file di origine, lo spazio dei nomi, routine o blocco.</span><span class="sxs-lookup"><span data-stu-id="d3385-174">This means the *declaration context* for a property must be a class, structure, module, or interface, and cannot be a source file, namespace, procedure, or block.</span></span> <span data-ttu-id="d3385-175">Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="d3385-175">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="d3385-176">Per impostazione predefinita, le proprietà utilizzano l'accesso pubblico.</span><span class="sxs-lookup"><span data-stu-id="d3385-176">By default, properties use public access.</span></span> <span data-ttu-id="d3385-177">È possibile modificare il livello di accesso di una proprietà con un modificatore di accesso sul `Property` istruzione ed è possibile impostare una delle routine della proprietà a un livello di accesso più restrittivo.</span><span class="sxs-lookup"><span data-stu-id="d3385-177">You can adjust a property's access level with an access modifier on the `Property` statement, and you can optionally adjust one of its property procedures to a more restrictive access level.</span></span>  
  
 <span data-ttu-id="d3385-178">Visual Basic passa un parametro per il `Set` procedura durante le assegnazioni di proprietà.</span><span class="sxs-lookup"><span data-stu-id="d3385-178">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="d3385-179">Se non si specifica un parametro per `Set`, l'ambiente di sviluppo integrato (IDE) usa un parametro implicito denominato `value`.</span><span class="sxs-lookup"><span data-stu-id="d3385-179">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="d3385-180">Questo parametro contiene il valore da assegnare alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="d3385-180">This parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="d3385-181">In genere archiviare il valore in una variabile locale privata e restituirlo ogni volta che il `Get` routine viene chiamata.</span><span class="sxs-lookup"><span data-stu-id="d3385-181">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="d3385-182">Regole</span><span class="sxs-lookup"><span data-stu-id="d3385-182">Rules</span></span>  
  
-   <span data-ttu-id="d3385-183">**Livelli di accesso misti.**</span><span class="sxs-lookup"><span data-stu-id="d3385-183">**Mixed Access Levels.**</span></span> <span data-ttu-id="d3385-184">Se si definisce una proprietà di lettura / scrittura, è possibile specificare facoltativamente un livello di accesso diverso per il `Get` o `Set` routine, ma non entrambi.</span><span class="sxs-lookup"><span data-stu-id="d3385-184">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="d3385-185">In questo caso, il livello di accesso della routine deve essere più restrittivo a livello di accesso della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d3385-185">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="d3385-186">Ad esempio, se viene dichiarata la proprietà `Friend`, è possibile dichiarare il `Set` procedura `Private`, ma non `Public`.</span><span class="sxs-lookup"><span data-stu-id="d3385-186">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="d3385-187">Se si sta definendo un `ReadOnly` o `WriteOnly` proprietà, la routine della proprietà singolo (`Get` o `Set`, rispettivamente) rappresenta tutte le proprietà.</span><span class="sxs-lookup"><span data-stu-id="d3385-187">If you are defining a `ReadOnly` or `WriteOnly` property, the single property procedure (`Get` or `Set`, respectively) represents all of the property.</span></span> <span data-ttu-id="d3385-188">È possibile dichiarare un livello di accesso diverso per una procedura, poiché verrebbero specificati due livelli di accesso per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="d3385-188">You cannot declare a different access level for such a procedure, because that would set two access levels for the property.</span></span>  
  
-   <span data-ttu-id="d3385-189">**Tipo restituito.**</span><span class="sxs-lookup"><span data-stu-id="d3385-189">**Return Type.**</span></span> <span data-ttu-id="d3385-190">Il `Property` istruzione può dichiarare il tipo di dati del valore restituito.</span><span class="sxs-lookup"><span data-stu-id="d3385-190">The `Property` statement can declare the data type of the value it returns.</span></span> <span data-ttu-id="d3385-191">È possibile specificare qualsiasi tipo di dati o il nome di un'enumerazione, struttura, classe o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d3385-191">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>  
  
     <span data-ttu-id="d3385-192">Se non si specifica `returntype`, la proprietà restituisce `Object`.</span><span class="sxs-lookup"><span data-stu-id="d3385-192">If you do not specify `returntype`, the property returns `Object`.</span></span>  
  
-   <span data-ttu-id="d3385-193">**Implementazione.**</span><span class="sxs-lookup"><span data-stu-id="d3385-193">**Implementation.**</span></span> <span data-ttu-id="d3385-194">Se questa proprietà Usa il `Implements` (parola chiave), classe o struttura deve avere un `Implements` istruzione immediatamente successiva relativo `Class` o `Structure` istruzione.</span><span class="sxs-lookup"><span data-stu-id="d3385-194">If this property uses the `Implements` keyword, the containing class or structure must have an `Implements` statement immediately following its `Class` or `Structure` statement.</span></span> <span data-ttu-id="d3385-195">Il `Implements` istruzione deve includere ogni interfaccia specificata in `implementslist`.</span><span class="sxs-lookup"><span data-stu-id="d3385-195">The `Implements` statement must include each interface specified in `implementslist`.</span></span> <span data-ttu-id="d3385-196">Tuttavia, il nome con cui si definisce un'interfaccia di `Property` (in `definedname`) non deve essere lo stesso nome di questa proprietà (in `name`).</span><span class="sxs-lookup"><span data-stu-id="d3385-196">However, the name by which an interface defines the `Property` (in `definedname`) does not have to be the same as the name of this property (in `name`).</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="d3385-197">Comportamento</span><span class="sxs-lookup"><span data-stu-id="d3385-197">Behavior</span></span>  
  
-   <span data-ttu-id="d3385-198">**Restituzione da una routine di proprietà.**</span><span class="sxs-lookup"><span data-stu-id="d3385-198">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="d3385-199">Quando il `Get` o `Set` routine restituisce al codice chiamante, l'esecuzione continua con l'istruzione successiva all'istruzione che ha richiamato.</span><span class="sxs-lookup"><span data-stu-id="d3385-199">When the `Get` or `Set` procedure returns to the calling code, execution continues with the statement following the statement that invoked it.</span></span>  
  
     <span data-ttu-id="d3385-200">Il `Exit Property` e `Return` istruzioni di uscire immediatamente da una routine di proprietà.</span><span class="sxs-lookup"><span data-stu-id="d3385-200">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="d3385-201">Un numero qualsiasi di `Exit Property` e `Return` istruzioni possono trovarsi in qualsiasi punto della procedura, ed è possibile combinare `Exit Property` e `Return` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="d3385-201">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
-   <span data-ttu-id="d3385-202">**Valore restituito.**</span><span class="sxs-lookup"><span data-stu-id="d3385-202">**Return Value.**</span></span> <span data-ttu-id="d3385-203">Per restituire un valore da un `Get` procedura, è possibile assegnare il valore per il nome della proprietà o includerlo in un `Return` istruzione.</span><span class="sxs-lookup"><span data-stu-id="d3385-203">To return a value from a `Get` procedure, you can either assign the value to the property name or include it in a `Return` statement.</span></span> <span data-ttu-id="d3385-204">Nell'esempio seguente viene assegnato il valore restituito per il nome della proprietà `quoteForTheDay` e quindi utilizza il `Exit Property` istruzione da restituire.</span><span class="sxs-lookup"><span data-stu-id="d3385-204">The following example assigns the return value to the property name `quoteForTheDay` and then uses the `Exit Property` statement to return.</span></span>  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#28](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_2.vb)]  
  
     <span data-ttu-id="d3385-205">Se si utilizza `Exit Property` senza assegnare un valore a `name`, `Get` procedura restituisce il valore predefinito per il tipo di dati della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d3385-205">If you use `Exit Property` without assigning a value to `name`, the `Get` procedure returns the default value for the property's data type.</span></span>  
  
     <span data-ttu-id="d3385-206">Il `Return` assegna istruzione allo stesso tempo la `Get` procedure restituire valore e di uscire dalla routine.</span><span class="sxs-lookup"><span data-stu-id="d3385-206">The `Return` statement at the same time assigns the `Get` procedure return value and exits the procedure.</span></span> <span data-ttu-id="d3385-207">Nell'esempio seguente viene illustrata questa operazione.</span><span class="sxs-lookup"><span data-stu-id="d3385-207">The following example shows this.</span></span>  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#29](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="d3385-208">Esempio</span><span class="sxs-lookup"><span data-stu-id="d3385-208">Example</span></span>  
 <span data-ttu-id="d3385-209">Nell'esempio seguente dichiara una proprietà in una classe.</span><span class="sxs-lookup"><span data-stu-id="d3385-209">The following example declares a property in a class.</span></span>  
  
 [!code-vb[VbVbalrStatements#51](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d3385-210">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3385-210">See Also</span></span>  
 [<span data-ttu-id="d3385-211">Proprietà implementate automaticamente</span><span class="sxs-lookup"><span data-stu-id="d3385-211">Auto-Implemented Properties</span></span>](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)  
 [<span data-ttu-id="d3385-212">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="d3385-212">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="d3385-213">Istruzione Get</span><span class="sxs-lookup"><span data-stu-id="d3385-213">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)  
 [<span data-ttu-id="d3385-214">Istruzione Set</span><span class="sxs-lookup"><span data-stu-id="d3385-214">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)  
 [<span data-ttu-id="d3385-215">Elenco dei parametri</span><span class="sxs-lookup"><span data-stu-id="d3385-215">Parameter List</span></span>](../../../visual-basic/language-reference/statements/parameter-list.md)  
 [<span data-ttu-id="d3385-216">Default</span><span class="sxs-lookup"><span data-stu-id="d3385-216">Default</span></span>](../../../visual-basic/language-reference/modifiers/default.md)
