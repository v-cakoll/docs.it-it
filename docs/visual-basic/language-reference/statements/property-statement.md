---
title: Istruzione Property | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.PropertySet
- vb.Property
- vb.PropertyGet
dev_langs:
- VB
helpviewer_keywords:
- Property statement
- default modifier
- property procedures, Property statements
- Property keyword
ms.assetid: 3155edaf-8ebd-45c6-9cef-11d5d2dc8d38
caps.latest.revision: 41
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: dbd779b4b6a1dd167e8581066b0fbe034cd2d8f2
ms.contentlocale: it-it
ms.lasthandoff: 05/23/2017

---
# <a name="property-statement"></a><span data-ttu-id="86585-102">Property Statement</span><span class="sxs-lookup"><span data-stu-id="86585-102">Property Statement</span></span>
<span data-ttu-id="86585-103">Dichiara il nome di una proprietà e le routine della proprietà usate per archiviare e recuperare il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="86585-103">Declares the name of a property, and the property procedures used to store and retrieve the value of the property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86585-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="86585-104">Syntax</span></span>  
  
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
  
## <a name="parts"></a><span data-ttu-id="86585-105">Parti</span><span class="sxs-lookup"><span data-stu-id="86585-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="86585-106">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="86585-106">Optional.</span></span> <span data-ttu-id="86585-107">Elenco di attributi applicabili a questa proprietà o `Get` o `Set` procedura.</span><span class="sxs-lookup"><span data-stu-id="86585-107">List of attributes that apply to this property or `Get` or `Set` procedure.</span></span> <span data-ttu-id="86585-108">Vedere [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="86585-108">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
-   `Default`  
  
     <span data-ttu-id="86585-109">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="86585-109">Optional.</span></span> <span data-ttu-id="86585-110">Specifica che questa proprietà è la proprietà predefinita per la classe o struttura in cui è definito.</span><span class="sxs-lookup"><span data-stu-id="86585-110">Specifies that this property is the default property for the class or structure on which it is defined.</span></span> <span data-ttu-id="86585-111">Valore predefinito deve accettare parametri e possono essere impostare e recuperare proprietà senza specificare il nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="86585-111">Default properties must accept parameters and can be set and retrieved without specifying the property name.</span></span> <span data-ttu-id="86585-112">Se si dichiara la proprietà come `Default`, non è possibile utilizzare `Private` sulla proprietà né sulle routine della proprietà.</span><span class="sxs-lookup"><span data-stu-id="86585-112">If you declare the property as `Default`, you cannot use `Private` on the property or on either of its property procedures.</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="86585-113">Facoltativo per il `Property` istruzione e almeno uno del `Get` e `Set` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="86585-113">Optional on the `Property` statement and on at most one of the `Get` and `Set` statements.</span></span> <span data-ttu-id="86585-114">Può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="86585-114">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="86585-115">Public</span><span class="sxs-lookup"><span data-stu-id="86585-115">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="86585-116">Protected</span><span class="sxs-lookup"><span data-stu-id="86585-116">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="86585-117">Friend</span><span class="sxs-lookup"><span data-stu-id="86585-117">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="86585-118">Private</span><span class="sxs-lookup"><span data-stu-id="86585-118">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     <span data-ttu-id="86585-119">Vedere [livelli in Visual Basic di accesso](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="86585-119">See [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `propertymodifiers`  
  
     <span data-ttu-id="86585-120">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="86585-120">Optional.</span></span> <span data-ttu-id="86585-121">Può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="86585-121">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="86585-122">Overload</span><span class="sxs-lookup"><span data-stu-id="86585-122">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [<span data-ttu-id="86585-123">Overrides</span><span class="sxs-lookup"><span data-stu-id="86585-123">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [<span data-ttu-id="86585-124">Overridable</span><span class="sxs-lookup"><span data-stu-id="86585-124">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [<span data-ttu-id="86585-125">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="86585-125">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="86585-126">MustOverride</span><span class="sxs-lookup"><span data-stu-id="86585-126">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="86585-127">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="86585-127">Optional.</span></span> <span data-ttu-id="86585-128">Vedere [condivisi](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="86585-128">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="86585-129">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="86585-129">Optional.</span></span> <span data-ttu-id="86585-130">Vedere [ombreggiature](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="86585-130">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `ReadOnly`  
  
     <span data-ttu-id="86585-131">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="86585-131">Optional.</span></span> <span data-ttu-id="86585-132">Vedere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="86585-132">See [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
-   `WriteOnly`  
  
     <span data-ttu-id="86585-133">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="86585-133">Optional.</span></span> <span data-ttu-id="86585-134">Vedere [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).</span><span class="sxs-lookup"><span data-stu-id="86585-134">See [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).</span></span>  
  
-   `Iterator`  
  
     <span data-ttu-id="86585-135">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="86585-135">Optional.</span></span> <span data-ttu-id="86585-136">Vedere [iteratore](../../../visual-basic/language-reference/modifiers/iterator.md).</span><span class="sxs-lookup"><span data-stu-id="86585-136">See [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="86585-137">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="86585-137">Required.</span></span> <span data-ttu-id="86585-138">Nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="86585-138">Name of the property.</span></span> <span data-ttu-id="86585-139">Vedere [dichiarati i nomi degli elementi](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="86585-139">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="86585-140">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="86585-140">Optional.</span></span> <span data-ttu-id="86585-141">Elenco di nomi di variabili locali che rappresenta i parametri di questa proprietà e gli eventuali parametri aggiuntivi di `Set` procedura.</span><span class="sxs-lookup"><span data-stu-id="86585-141">List of local variable names representing the parameters of this property, and possible additional parameters of the `Set` procedure.</span></span> <span data-ttu-id="86585-142">Vedere [elenco parametri](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="86585-142">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>  
  
-   `returntype`  
  
     <span data-ttu-id="86585-143">Obbligatorio se `Option``Strict` è `On`.</span><span class="sxs-lookup"><span data-stu-id="86585-143">Required if `Option``Strict` is `On`.</span></span> <span data-ttu-id="86585-144">Tipo di dati del valore restituito da questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="86585-144">Data type of the value returned by this property.</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="86585-145">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="86585-145">Optional.</span></span> <span data-ttu-id="86585-146">Indica che questa proprietà implementa una o più proprietà, ognuna definita in un'interfaccia implementata dalla classe o struttura contenente questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="86585-146">Indicates that this property implements one or more properties, each one defined in an interface implemented by this property's containing class or structure.</span></span> <span data-ttu-id="86585-147">Vedere [implementa istruzione](../../../visual-basic/language-reference/statements/implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="86585-147">See [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="86585-148">Necessario se si fornisce `Implements`.</span><span class="sxs-lookup"><span data-stu-id="86585-148">Required if `Implements` is supplied.</span></span> <span data-ttu-id="86585-149">Elenco delle proprietà in fase di implementazione.</span><span class="sxs-lookup"><span data-stu-id="86585-149">List of properties being implemented.</span></span>  
  
     `implementedproperty [ , implementedproperty ... ]`  
  
     <span data-ttu-id="86585-150">Ogni `implementedproperty` presenta la sintassi e le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="86585-150">Each `implementedproperty` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="86585-151">Parte</span><span class="sxs-lookup"><span data-stu-id="86585-151">Part</span></span>|<span data-ttu-id="86585-152">Descrizione</span><span class="sxs-lookup"><span data-stu-id="86585-152">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="86585-153">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="86585-153">Required.</span></span> <span data-ttu-id="86585-154">Nome di un'interfaccia implementata da questa proprietà contenente classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="86585-154">Name of an interface implemented by this property's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="86585-155">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="86585-155">Required.</span></span> <span data-ttu-id="86585-156">Nome con cui la proprietà è definita in `interface`.</span><span class="sxs-lookup"><span data-stu-id="86585-156">Name by which the property is defined in `interface`.</span></span>|  
  
-   `Get`  
  
     <span data-ttu-id="86585-157">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="86585-157">Optional.</span></span> <span data-ttu-id="86585-158">Obbligatorio se la proprietà è contrassegnata `WriteOnly`.</span><span class="sxs-lookup"><span data-stu-id="86585-158">Required if the property is marked `WriteOnly`.</span></span> <span data-ttu-id="86585-159">Avvia un `Get` routine di proprietà che viene utilizzata per restituire il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="86585-159">Starts a `Get` property procedure that is used to return the value of the property.</span></span>  
  
-   `statements`  
  
     <span data-ttu-id="86585-160">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="86585-160">Optional.</span></span> <span data-ttu-id="86585-161">Blocco di istruzioni da eseguire all'interno di `Get` o `Set` procedura.</span><span class="sxs-lookup"><span data-stu-id="86585-161">Block of statements to run within the `Get` or `Set` procedure.</span></span>  
  
-   `End Get`  
  
     <span data-ttu-id="86585-162">Termina la `Get` routine di proprietà.</span><span class="sxs-lookup"><span data-stu-id="86585-162">Terminates the `Get` property procedure.</span></span>  
  
-   `Set`  
  
     <span data-ttu-id="86585-163">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="86585-163">Optional.</span></span> <span data-ttu-id="86585-164">Obbligatorio se la proprietà è contrassegnata `ReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="86585-164">Required if the property is marked `ReadOnly`.</span></span> <span data-ttu-id="86585-165">Avvia un `Set` routine di proprietà che viene utilizzata per archiviare il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="86585-165">Starts a `Set` property procedure that is used to store the value of the property.</span></span>  
  
-   `End Set`  
  
     <span data-ttu-id="86585-166">Termina la `Set` routine di proprietà.</span><span class="sxs-lookup"><span data-stu-id="86585-166">Terminates the `Set` property procedure.</span></span>  
  
-   `End Property`  
  
     <span data-ttu-id="86585-167">Termina la definizione di questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="86585-167">Terminates the definition of this property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86585-168">Note</span><span class="sxs-lookup"><span data-stu-id="86585-168">Remarks</span></span>  
 <span data-ttu-id="86585-169">Il `Property` istruzione introduce la dichiarazione di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="86585-169">The `Property` statement introduces the declaration of a property.</span></span> <span data-ttu-id="86585-170">Una proprietà può avere un `Get` procedura (sola lettura), un `Set` procedure (sola scrittura) o entrambe (lettura-scrittura).</span><span class="sxs-lookup"><span data-stu-id="86585-170">A property can have a `Get` procedure (read only), a `Set` procedure (write only), or both (read-write).</span></span> <span data-ttu-id="86585-171">È possibile omettere il `Get` e `Set` procedura quando si utilizza una proprietà implementata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="86585-171">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="86585-172">Per ulteriori informazioni, vedere [proprietà implementate automaticamente](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="86585-172">For more information, see [Auto-Implemented Properties](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>  
  
 <span data-ttu-id="86585-173">È possibile utilizzare `Property` solo a livello di classe.</span><span class="sxs-lookup"><span data-stu-id="86585-173">You can use `Property` only at class level.</span></span> <span data-ttu-id="86585-174">Ciò significa che il *contesto della dichiarazione* per una proprietà deve essere una classe, struttura, modulo o interfaccia e non può essere un file di origine, lo spazio dei nomi, routine o blocco.</span><span class="sxs-lookup"><span data-stu-id="86585-174">This means the *declaration context* for a property must be a class, structure, module, or interface, and cannot be a source file, namespace, procedure, or block.</span></span> <span data-ttu-id="86585-175">Per ulteriori informazioni, vedere [contesti delle dichiarazioni e livelli di accesso predefinito](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="86585-175">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="86585-176">Per impostazione predefinita, le proprietà utilizzano l'accesso pubblico.</span><span class="sxs-lookup"><span data-stu-id="86585-176">By default, properties use public access.</span></span> <span data-ttu-id="86585-177">È possibile modificare il livello di accesso della proprietà con un modificatore di accesso nella `Property` istruzione ed è possibile impostare una delle routine della proprietà a un livello di accesso più restrittivo.</span><span class="sxs-lookup"><span data-stu-id="86585-177">You can adjust a property's access level with an access modifier on the `Property` statement, and you can optionally adjust one of its property procedures to a more restrictive access level.</span></span>  
  
 <span data-ttu-id="86585-178">Visual Basic passa un parametro per il `Set` procedura durante le assegnazioni di proprietà.</span><span class="sxs-lookup"><span data-stu-id="86585-178">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="86585-179">Se non si fornisce un parametro per `Set`, l'ambiente di sviluppo integrato (IDE) utilizza un parametro implicito denominato `value`.</span><span class="sxs-lookup"><span data-stu-id="86585-179">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="86585-180">Questo parametro contiene il valore da assegnare alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="86585-180">This parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="86585-181">In genere questo valore in una variabile locale privata e restituirlo ogni volta che il `Get` routine viene chiamata.</span><span class="sxs-lookup"><span data-stu-id="86585-181">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="86585-182">Regole</span><span class="sxs-lookup"><span data-stu-id="86585-182">Rules</span></span>  
  
-   <span data-ttu-id="86585-183">**Livelli di accesso misti.**</span><span class="sxs-lookup"><span data-stu-id="86585-183">**Mixed Access Levels.**</span></span> <span data-ttu-id="86585-184">Se si definisce una proprietà di lettura / scrittura, è possibile specificare facoltativamente un livello di accesso diversi per il `Get` o `Set` procedura, ma non entrambi.</span><span class="sxs-lookup"><span data-stu-id="86585-184">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="86585-185">In questo caso, il livello di accesso procedura deve essere più restrittivo rispetto a livello di accesso della proprietà.</span><span class="sxs-lookup"><span data-stu-id="86585-185">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="86585-186">Ad esempio, se viene dichiarata la proprietà `Friend`, è possibile dichiarare il `Set` procedura `Private`, ma non `Public`.</span><span class="sxs-lookup"><span data-stu-id="86585-186">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="86585-187">Se si sta definendo un `ReadOnly` o `WriteOnly` proprietà, la procedura singola proprietà (`Get` o `Set`, rispettivamente) rappresenta tutte le proprietà.</span><span class="sxs-lookup"><span data-stu-id="86585-187">If you are defining a `ReadOnly` or `WriteOnly` property, the single property procedure (`Get` or `Set`, respectively) represents all of the property.</span></span> <span data-ttu-id="86585-188">È possibile dichiarare un livello di accesso diversi per tale procedura, poiché verrebbero specificati due livelli di accesso per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="86585-188">You cannot declare a different access level for such a procedure, because that would set two access levels for the property.</span></span>  
  
-   <span data-ttu-id="86585-189">**Tipo restituito.**</span><span class="sxs-lookup"><span data-stu-id="86585-189">**Return Type.**</span></span> <span data-ttu-id="86585-190">Il `Property` istruzione può dichiarare il tipo di dati del valore restituito.</span><span class="sxs-lookup"><span data-stu-id="86585-190">The `Property` statement can declare the data type of the value it returns.</span></span> <span data-ttu-id="86585-191">È possibile specificare qualsiasi tipo di dati o il nome di un'enumerazione, struttura, classe o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="86585-191">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>  
  
     <span data-ttu-id="86585-192">Se non si specifica `returntype`, la proprietà restituisce `Object`.</span><span class="sxs-lookup"><span data-stu-id="86585-192">If you do not specify `returntype`, the property returns `Object`.</span></span>  
  
-   <span data-ttu-id="86585-193">**Implementazione.**</span><span class="sxs-lookup"><span data-stu-id="86585-193">**Implementation.**</span></span> <span data-ttu-id="86585-194">Se questa proprietà viene utilizzata la `Implements` (parola chiave), classe o struttura deve avere un `Implements` istruzione immediatamente successiva relativo `Class` o `Structure` istruzione.</span><span class="sxs-lookup"><span data-stu-id="86585-194">If this property uses the `Implements` keyword, the containing class or structure must have an `Implements` statement immediately following its `Class` or `Structure` statement.</span></span> <span data-ttu-id="86585-195">Il `Implements` istruzione deve includere ogni interfaccia specificata in `implementslist`.</span><span class="sxs-lookup"><span data-stu-id="86585-195">The `Implements` statement must include each interface specified in `implementslist`.</span></span> <span data-ttu-id="86585-196">Tuttavia, il nome con cui si definisce un'interfaccia di `Property` (in `definedname`) non deve essere lo stesso nome di questa proprietà (in `name`).</span><span class="sxs-lookup"><span data-stu-id="86585-196">However, the name by which an interface defines the `Property` (in `definedname`) does not have to be the same as the name of this property (in `name`).</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="86585-197">Comportamento</span><span class="sxs-lookup"><span data-stu-id="86585-197">Behavior</span></span>  
  
-   <span data-ttu-id="86585-198">**Restituzione da una routine di proprietà.**</span><span class="sxs-lookup"><span data-stu-id="86585-198">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="86585-199">Quando il `Get` o `Set` procedure restituisce al codice chiamante, l'esecuzione continua con l'istruzione successiva all'istruzione che ha richiamato.</span><span class="sxs-lookup"><span data-stu-id="86585-199">When the `Get` or `Set` procedure returns to the calling code, execution continues with the statement following the statement that invoked it.</span></span>  
  
     <span data-ttu-id="86585-200">Il `Exit Property` e `Return` istruzioni di uscire immediatamente da una routine di proprietà.</span><span class="sxs-lookup"><span data-stu-id="86585-200">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="86585-201">Un numero qualsiasi di `Exit Property` e `Return` istruzioni possono trovarsi in qualsiasi punto della procedura, ed è possibile combinare `Exit Property` e `Return` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="86585-201">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
-   <span data-ttu-id="86585-202">**Valore restituito.**</span><span class="sxs-lookup"><span data-stu-id="86585-202">**Return Value.**</span></span> <span data-ttu-id="86585-203">Per restituire un valore da un `Get` procedura, è possibile assegnare il valore per il nome della proprietà o includerlo in un `Return` istruzione.</span><span class="sxs-lookup"><span data-stu-id="86585-203">To return a value from a `Get` procedure, you can either assign the value to the property name or include it in a `Return` statement.</span></span> <span data-ttu-id="86585-204">Nell'esempio seguente assegna il valore restituito per il nome della proprietà `quoteForTheDay` e quindi utilizza il `Exit Property` istruzione per la restituzione.</span><span class="sxs-lookup"><span data-stu-id="86585-204">The following example assigns the return value to the property name `quoteForTheDay` and then uses the `Exit Property` statement to return.</span></span>  
  
     <span data-ttu-id="86585-205">[!code-vb[VbVbalrStatements&#27;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="86585-205">[!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]</span></span>  
  
     <span data-ttu-id="86585-206">[!code-vb[28 VbVbalrStatements](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="86585-206">[!code-vb[VbVbalrStatements#28](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_2.vb)]</span></span>  
  
     <span data-ttu-id="86585-207">Se si utilizza `Exit Property` senza assegnare un valore a `name`, `Get` procedura restituisce il valore predefinito per il tipo di dati della proprietà.</span><span class="sxs-lookup"><span data-stu-id="86585-207">If you use `Exit Property` without assigning a value to `name`, the `Get` procedure returns the default value for the property's data type.</span></span>  
  
     <span data-ttu-id="86585-208">Il `Return` assegna istruzione allo stesso tempo la `Get` procedure restituire valore ed esce dalla procedura.</span><span class="sxs-lookup"><span data-stu-id="86585-208">The `Return` statement at the same time assigns the `Get` procedure return value and exits the procedure.</span></span> <span data-ttu-id="86585-209">Nell'esempio seguente viene illustrata questa operazione.</span><span class="sxs-lookup"><span data-stu-id="86585-209">The following example shows this.</span></span>  
  
     <span data-ttu-id="86585-210">[!code-vb[VbVbalrStatements&#27;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="86585-210">[!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]</span></span>  
  
     <span data-ttu-id="86585-211">[!code-vb[VbVbalrStatements&#29;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="86585-211">[!code-vb[VbVbalrStatements#29](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_3.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="86585-212">Esempio</span><span class="sxs-lookup"><span data-stu-id="86585-212">Example</span></span>  
 <span data-ttu-id="86585-213">Nell'esempio seguente dichiara una proprietà in una classe.</span><span class="sxs-lookup"><span data-stu-id="86585-213">The following example declares a property in a class.</span></span>  
  
 <span data-ttu-id="86585-214">[!code-vb[51 VbVbalrStatements](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="86585-214">[!code-vb[VbVbalrStatements#51](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_4.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86585-215">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86585-215">See Also</span></span>  
 <span data-ttu-id="86585-216">[Proprietà implementate automaticamente](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md) </span><span class="sxs-lookup"><span data-stu-id="86585-216">[Auto-Implemented Properties](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md) </span></span>  
<span data-ttu-id="86585-217"> [Oggetti e classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span><span class="sxs-lookup"><span data-stu-id="86585-217"> [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span></span>  
<span data-ttu-id="86585-218"> [Get (istruzione)](../../../visual-basic/language-reference/statements/get-statement.md) </span><span class="sxs-lookup"><span data-stu-id="86585-218"> [Get Statement](../../../visual-basic/language-reference/statements/get-statement.md) </span></span>  
<span data-ttu-id="86585-219"> [Set (istruzione)](../../../visual-basic/language-reference/statements/set-statement.md) </span><span class="sxs-lookup"><span data-stu-id="86585-219"> [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md) </span></span>  
<span data-ttu-id="86585-220"> [Elenco di parametri](../../../visual-basic/language-reference/statements/parameter-list.md) </span><span class="sxs-lookup"><span data-stu-id="86585-220"> [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md) </span></span>  
<span data-ttu-id="86585-221"> [Default](../../../visual-basic/language-reference/modifiers/default.md)</span><span class="sxs-lookup"><span data-stu-id="86585-221"> [Default](../../../visual-basic/language-reference/modifiers/default.md)</span></span>

