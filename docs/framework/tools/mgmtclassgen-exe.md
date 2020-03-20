---
title: Mgmtclassgen.exe (Management Strongly Typed Class Generator)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CIM types
- Management Strongly Typed Class Generator
- WMI class
- Mgmtclassgen.exe
- early-bound managed classes
ms.assetid: 02ce6699-49b5-4a0b-b0d5-1003c491232e
ms.openlocfilehash: 5e39670fbb40acb999a243ac86683219f3c89e4f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180375"
---
# <a name="mgmtclassgenexe-management-strongly-typed-class-generator"></a><span data-ttu-id="56719-102">Mgmtclassgen.exe (Management Strongly Typed Class Generator)</span><span class="sxs-lookup"><span data-stu-id="56719-102">Mgmtclassgen.exe (Management Strongly Typed Class Generator)</span></span>
<span data-ttu-id="56719-103">Lo strumento Generatore di classi di gestione fortemente tipizzate consente di generare velocemente una classe gestita ad associazione precoce per una specifica classe WMI (Windows Management Instrumentation, Strumentazione gestita Windows).</span><span class="sxs-lookup"><span data-stu-id="56719-103">The Management Strongly Typed Class Generator tool enables you to quickly generate an early-bound managed class for a specified Windows Management Instrumentation (WMI) class.</span></span> <span data-ttu-id="56719-104">L'utilizzo della classe generata semplifica la scrittura del codice per l'accesso a un'istanza della classe WMI.</span><span class="sxs-lookup"><span data-stu-id="56719-104">The generated class simplifies the code you must write to access an instance of the WMI class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56719-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="56719-105">Syntax</span></span>  
  
```console  
mgmtclassgen
WMIClass [options]
```  
  
|<span data-ttu-id="56719-106">Argomento</span><span class="sxs-lookup"><span data-stu-id="56719-106">Argument</span></span>|<span data-ttu-id="56719-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="56719-107">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="56719-108">*classeWMI*</span><span class="sxs-lookup"><span data-stu-id="56719-108">*WMIClass*</span></span>|<span data-ttu-id="56719-109">Classe WMI per la quale generare una classe gestita ad associazione precoce.</span><span class="sxs-lookup"><span data-stu-id="56719-109">The Windows Management Instrumentation class for which to generate an early-bound managed class.</span></span>|  
  
|<span data-ttu-id="56719-110">Opzione</span><span class="sxs-lookup"><span data-stu-id="56719-110">Option</span></span>|<span data-ttu-id="56719-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="56719-111">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="56719-112">**/l**  *linguaggio*</span><span class="sxs-lookup"><span data-stu-id="56719-112">**/l**  *language*</span></span>|<span data-ttu-id="56719-113">Specifica il linguaggio in cui generare la classe gestita ad associazione precoce.</span><span class="sxs-lookup"><span data-stu-id="56719-113">Specifies the language in which to generate the early-bound managed class.</span></span> <span data-ttu-id="56719-114">È possibile specificare **CS** (C#; impostazione predefinita), **VB** (Visual Basic),  **MC** (C++) o  **JS** (JScript) come argomento del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="56719-114">You can specify **CS** (C#; default), **VB** (Visual Basic),  **MC** (C++), or **JS** (JScript) as the language argument.</span></span>|  
|<span data-ttu-id="56719-115">**/m**  *computer*</span><span class="sxs-lookup"><span data-stu-id="56719-115">**/m**  *machine*</span></span>|<span data-ttu-id="56719-116">Specifica il computer al quale eseguire la connessione ovvero quello sul quale risiede la classe WMI.</span><span class="sxs-lookup"><span data-stu-id="56719-116">Specifies the computer to connect to, where the WMI class resides.</span></span> <span data-ttu-id="56719-117">Il valore predefinito è il computer locale.</span><span class="sxs-lookup"><span data-stu-id="56719-117">The default is the local computer.</span></span>|  
|<span data-ttu-id="56719-118">**/n**  *percorso*</span><span class="sxs-lookup"><span data-stu-id="56719-118">**/n**  *path*</span></span>|<span data-ttu-id="56719-119">Specifica il percorso dello spazio dei nomi WMI contenente la classe WMI.</span><span class="sxs-lookup"><span data-stu-id="56719-119">Specifies the path to the WMI namespace that contains the WMI class.</span></span> <span data-ttu-id="56719-120">Se non si specifica questa opzione, lo strumento genera codice per *classeWMI* nello spazio dei nomi **Root\cimv2** predefinito.</span><span class="sxs-lookup"><span data-stu-id="56719-120">If you do not specify this option, the tool generates code for *WMIClass* in the default **Root\cimv2** namespace.</span></span>|  
|<span data-ttu-id="56719-121">**/o**  *spazionomiclasse*</span><span class="sxs-lookup"><span data-stu-id="56719-121">**/o**  *classnamespace*</span></span>|<span data-ttu-id="56719-122">Specifica lo spazio dei nomi .NET nel quale generare la classe di codice gestito.</span><span class="sxs-lookup"><span data-stu-id="56719-122">Specifies the .NET namespace in which to generate the managed code class.</span></span> <span data-ttu-id="56719-123">Se non si specifica questa opzione, lo spazio dei nomi verrà generato utilizzando lo spazio dei nomi WMI e il prefisso dello schema.</span><span class="sxs-lookup"><span data-stu-id="56719-123">If you do not specify this option, the tool generates the namespace using the WMI namespace and the schema prefix.</span></span> <span data-ttu-id="56719-124">Il prefisso dello schema è la parte del nome della classe che precede il carattere di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="56719-124">The schema prefix is the part of the class name preceding the underscore character.</span></span> <span data-ttu-id="56719-125">Ad esempio, per la classe **Win32_OperatingSystem** nello spazio dei nomi **Root\cimv2**, lo strumento genera la classe in **ROOT.CIMV2.Win32**.</span><span class="sxs-lookup"><span data-stu-id="56719-125">For example, for the **Win32_OperatingSystem** class in the **Root\cimv2** namespace, the tool would generate the class in **ROOT.CIMV2.Win32**.</span></span>|  
|<span data-ttu-id="56719-126">**/p**  *percorsofile*</span><span class="sxs-lookup"><span data-stu-id="56719-126">**/p**  *filepath*</span></span>|<span data-ttu-id="56719-127">Specifica il percorso del file in cui salvare il codice generato.</span><span class="sxs-lookup"><span data-stu-id="56719-127">Specifies the path to the file in which to save the generated code.</span></span> <span data-ttu-id="56719-128">Se non si specifica questa opzione, il file verrà creato nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="56719-128">If you do not specify this option, the tool creates the file in the current directory.</span></span> <span data-ttu-id="56719-129">Denomina la classe e il file in cui viene generata la classe con l'argomento *classeWMI*.</span><span class="sxs-lookup"><span data-stu-id="56719-129">It names the class and file in which it generates the class using the *WMIClass* argument.</span></span> <span data-ttu-id="56719-130">Il nome della classe e del file è uguale al nome di *classeWMI*.</span><span class="sxs-lookup"><span data-stu-id="56719-130">The name of the class and the file are the same as the name of the *WMIClass.*</span></span> <span data-ttu-id="56719-131">Se il nome di *classeWMI* include un carattere di sottolineatura, lo strumento usa la parte del nome della classe che segue tale carattere.</span><span class="sxs-lookup"><span data-stu-id="56719-131">If *WMIClass* contains an underscore character, the tool uses the part of the class name following the underscore character.</span></span> <span data-ttu-id="56719-132">Ad esempio, se il nome di *classeWMI* è nel formato **Win32_LogicalDisk**, il nome della classe e del file generati sarà "logicaldisk".</span><span class="sxs-lookup"><span data-stu-id="56719-132">For example, if the *WMIClass* name is in the format **Win32_LogicalDisk**, the generated class and file is named "logicaldisk".</span></span> <span data-ttu-id="56719-133">Se esiste già un file con tale nome, verrà sovrascritto.</span><span class="sxs-lookup"><span data-stu-id="56719-133">If a file already exists, the tool overwrites the existing file.</span></span>|  
|<span data-ttu-id="56719-134">**/pw**  *password*</span><span class="sxs-lookup"><span data-stu-id="56719-134">**/pw**  *password*</span></span>|<span data-ttu-id="56719-135">Specifica la password da usare per l'accesso a un computer specificato dall'opzione **/m**.</span><span class="sxs-lookup"><span data-stu-id="56719-135">Specifies the password to use when logging on to a computer specified by the **/m** option.</span></span>|  
|<span data-ttu-id="56719-136">**/u**  *nomeutente*</span><span class="sxs-lookup"><span data-stu-id="56719-136">**/u**  *user name*</span></span>|<span data-ttu-id="56719-137">Specifica il nome utente da usare per l'accesso a un computer specificato dall'opzione **/m**.</span><span class="sxs-lookup"><span data-stu-id="56719-137">Specifies the user name to use when logging on to a computer specified by the **/m** option.</span></span>|  
|<span data-ttu-id="56719-138">**/?**</span><span class="sxs-lookup"><span data-stu-id="56719-138">**/?**</span></span>|<span data-ttu-id="56719-139">Visualizza la sintassi e le opzioni di comando dello strumento.</span><span class="sxs-lookup"><span data-stu-id="56719-139">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56719-140">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="56719-140">Remarks</span></span>  
 <span data-ttu-id="56719-141">Mgmtclassgen.exe utilizza il metodo <xref:System.Management.ManagementClass.GetStronglyTypedClassCode%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="56719-141">Mgmtclassgen.exe uses the <xref:System.Management.ManagementClass.GetStronglyTypedClassCode%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="56719-142">È possibile pertanto utilizzare un provider di codice personalizzato per generare codice in linguaggi gestiti diversi da C#, Visual Basic e JScript.</span><span class="sxs-lookup"><span data-stu-id="56719-142">Therefore, you can use any custom code provider to generate code in managed languages other than C#, Visual Basic, and JScript.</span></span>  
  
 <span data-ttu-id="56719-143">Le classi generate sono associate allo schema per il quale sono state generate.</span><span class="sxs-lookup"><span data-stu-id="56719-143">Note that generated classes are bound to the schema for which they are generated.</span></span> <span data-ttu-id="56719-144">Quando lo schema sottostante una classe viene modificato è necessario generare nuovamente la classe se si desidera che essa rispecchi le modifiche dello schema.</span><span class="sxs-lookup"><span data-stu-id="56719-144">If the underlying schema changes, you must regenerate the class if you want it to reflect changes to the schema.</span></span>  
  
 <span data-ttu-id="56719-145">Nella tabella riportata di seguito viene illustrato il mapping tra i tipi CIM (Common Information Model) WMI e i tipi dati inclusi in una classe generata.</span><span class="sxs-lookup"><span data-stu-id="56719-145">The following table shows how WMI Common Information Model (CIM) types map to data types in a generated class:</span></span>  
  
|<span data-ttu-id="56719-146">Tipo CIM</span><span class="sxs-lookup"><span data-stu-id="56719-146">CIM type</span></span>|<span data-ttu-id="56719-147">Tipo di dati incluso nella classe generata</span><span class="sxs-lookup"><span data-stu-id="56719-147">Data type in the generated class</span></span>|  
|--------------|--------------------------------------|  
|<span data-ttu-id="56719-148">CIM_SINT8</span><span class="sxs-lookup"><span data-stu-id="56719-148">CIM_SINT8</span></span>|<span data-ttu-id="56719-149">**Sbyte**</span><span class="sxs-lookup"><span data-stu-id="56719-149">**SByte**</span></span>|  
|<span data-ttu-id="56719-150">CIM_UINT8</span><span class="sxs-lookup"><span data-stu-id="56719-150">CIM_UINT8</span></span>|<span data-ttu-id="56719-151">**Byte**</span><span class="sxs-lookup"><span data-stu-id="56719-151">**Byte**</span></span>|  
|<span data-ttu-id="56719-152">CIM_SINT16</span><span class="sxs-lookup"><span data-stu-id="56719-152">CIM_SINT16</span></span>|<span data-ttu-id="56719-153">**Int16**</span><span class="sxs-lookup"><span data-stu-id="56719-153">**Int16**</span></span>|  
|<span data-ttu-id="56719-154">CIM_UINT16</span><span class="sxs-lookup"><span data-stu-id="56719-154">CIM_UINT16</span></span>|<span data-ttu-id="56719-155">**UInt16**</span><span class="sxs-lookup"><span data-stu-id="56719-155">**UInt16**</span></span>|  
|<span data-ttu-id="56719-156">CIM_SINT32</span><span class="sxs-lookup"><span data-stu-id="56719-156">CIM_SINT32</span></span>|<span data-ttu-id="56719-157">**Int32**</span><span class="sxs-lookup"><span data-stu-id="56719-157">**Int32**</span></span>|  
|<span data-ttu-id="56719-158">SIM_UINT32</span><span class="sxs-lookup"><span data-stu-id="56719-158">SIM_UINT32</span></span>|<span data-ttu-id="56719-159">**UInt32**</span><span class="sxs-lookup"><span data-stu-id="56719-159">**UInt32**</span></span>|  
|<span data-ttu-id="56719-160">CIM_SINT64</span><span class="sxs-lookup"><span data-stu-id="56719-160">CIM_SINT64</span></span>|<span data-ttu-id="56719-161">**Int64**</span><span class="sxs-lookup"><span data-stu-id="56719-161">**Int64**</span></span>|  
|<span data-ttu-id="56719-162">CIM_UINT64</span><span class="sxs-lookup"><span data-stu-id="56719-162">CIM_UINT64</span></span>|<span data-ttu-id="56719-163">**UInt64**</span><span class="sxs-lookup"><span data-stu-id="56719-163">**UInt64**</span></span>|  
|<span data-ttu-id="56719-164">CIM_REAL32</span><span class="sxs-lookup"><span data-stu-id="56719-164">CIM_REAL32</span></span>|<span data-ttu-id="56719-165">**Singolo**</span><span class="sxs-lookup"><span data-stu-id="56719-165">**Single**</span></span>|  
|<span data-ttu-id="56719-166">CIM_REAL64</span><span class="sxs-lookup"><span data-stu-id="56719-166">CIM_REAL64</span></span>|<span data-ttu-id="56719-167">**Doppia**</span><span class="sxs-lookup"><span data-stu-id="56719-167">**Double**</span></span>|  
|<span data-ttu-id="56719-168">CIM_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="56719-168">CIM_BOOLEAN</span></span>|<span data-ttu-id="56719-169">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="56719-169">**Boolean**</span></span>|  
|<span data-ttu-id="56719-170">CIM_String</span><span class="sxs-lookup"><span data-stu-id="56719-170">CIM_String</span></span>|<span data-ttu-id="56719-171">**Stringa**</span><span class="sxs-lookup"><span data-stu-id="56719-171">**String**</span></span>|  
|<span data-ttu-id="56719-172">CIM_DATETIME</span><span class="sxs-lookup"><span data-stu-id="56719-172">CIM_DATETIME</span></span>|<span data-ttu-id="56719-173">**DateTime** o **TimeSpan**</span><span class="sxs-lookup"><span data-stu-id="56719-173">**DateTime** or **TimeSpan**</span></span>|  
|<span data-ttu-id="56719-174">CIM_REFERENCE</span><span class="sxs-lookup"><span data-stu-id="56719-174">CIM_REFERENCE</span></span>|<span data-ttu-id="56719-175">**ManagementPath**</span><span class="sxs-lookup"><span data-stu-id="56719-175">**ManagementPath**</span></span>|  
|<span data-ttu-id="56719-176">CIM_CHAR16</span><span class="sxs-lookup"><span data-stu-id="56719-176">CIM_CHAR16</span></span>|<span data-ttu-id="56719-177">**Char**</span><span class="sxs-lookup"><span data-stu-id="56719-177">**Char**</span></span>|  
|<span data-ttu-id="56719-178">CIM_OBJECT</span><span class="sxs-lookup"><span data-stu-id="56719-178">CIM_OBJECT</span></span>|<span data-ttu-id="56719-179">**ManagementBaseObject**</span><span class="sxs-lookup"><span data-stu-id="56719-179">**ManagementBaseObject**</span></span>|  
|<span data-ttu-id="56719-180">CIM_IUNKNOWN</span><span class="sxs-lookup"><span data-stu-id="56719-180">CIM_IUNKNOWN</span></span>|<span data-ttu-id="56719-181">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="56719-181">**Object**</span></span>|  
|<span data-ttu-id="56719-182">CIM_ARRAY</span><span class="sxs-lookup"><span data-stu-id="56719-182">CIM_ARRAY</span></span>|<span data-ttu-id="56719-183">Matrice degli oggetti precedenti</span><span class="sxs-lookup"><span data-stu-id="56719-183">Array of the above mentioned objects</span></span>|  
  
 <span data-ttu-id="56719-184">Quando viene generata una classe WMI può accadere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="56719-184">Note the following behaviors when you generate a WMI class:</span></span>  
  
- <span data-ttu-id="56719-185">Una proprietà o un metodo pubblico standard può avere lo stesso nome di una proprietà o di un metodo esistente.</span><span class="sxs-lookup"><span data-stu-id="56719-185">It is possible for a standard public property or method to have the same name as an existing property or method.</span></span> <span data-ttu-id="56719-186">In tal caso il nome della proprietà o del metodo nella classe generata verrà automaticamente cambiato per evitare conflitti di denominazione.</span><span class="sxs-lookup"><span data-stu-id="56719-186">If this occurs, the tool changes the name of the property or method in the generated class to avoid naming conflicts.</span></span>  
  
- <span data-ttu-id="56719-187">Il nome di una proprietà o di un metodo in una classe generata può essere una parola chiave nel linguaggio di programmazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="56719-187">It is possible for the name of a property or method in a generated class to be a keyword in the target programming language.</span></span> <span data-ttu-id="56719-188">In tal caso il nome della proprietà o del metodo nella classe generata verrà automaticamente cambiato per evitare conflitti di denominazione.</span><span class="sxs-lookup"><span data-stu-id="56719-188">If this occurs, the tool changes the name of the property or method in the generated class to avoid naming conflicts.</span></span>  
  
- <span data-ttu-id="56719-189">In WMI un qualificatore è un modificatore contenente informazioni per descrivere una classe, un'istanza, una proprietà o un metodo.</span><span class="sxs-lookup"><span data-stu-id="56719-189">In WMI, qualifiers are modifiers that contain information to describe a class, instance, property, or method.</span></span> <span data-ttu-id="56719-190">Per descrivere una proprietà in una classe generata, WMI usa qualificatori standard quali **Read**, **Write** e **Key**.</span><span class="sxs-lookup"><span data-stu-id="56719-190">WMI uses standard qualifiers such as **Read**, **Write**, and **Key** to describe a property in a generated class.</span></span> <span data-ttu-id="56719-191">Ad esempio, una proprietà modificata con il qualificatore **Read** viene definita solo con una funzione di accesso **get** della proprietà nella classe generata.</span><span class="sxs-lookup"><span data-stu-id="56719-191">For example, a property that is modified with a **Read** qualifier is defined only with a property **get** accessor in the generated class.</span></span> <span data-ttu-id="56719-192">Poiché una proprietà contrassegnata dal qualificatore **Read** è di sola lettura, non viene definita alcuna funzione di accesso **set**.</span><span class="sxs-lookup"><span data-stu-id="56719-192">Because a property marked with the **Read** qualifier is intended to be read-only, a **set** accessor is not defined.</span></span>  
  
- <span data-ttu-id="56719-193">Una proprietà numerica può essere modificata tramite i qualificatori **Values** e **ValueMaps** per indicare che la proprietà può essere impostata solo su specifici valori consentiti.</span><span class="sxs-lookup"><span data-stu-id="56719-193">A numeric property can be modified by the **Values** and **ValueMaps** qualifiers to indicate that the property can be set only to specified permissible values.</span></span> <span data-ttu-id="56719-194">Viene generata un'enumerazione con i qualificatori **Values** e **ValueMaps** e viene eseguito il mapping della proprietà all'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="56719-194">An enumeration is generated with these **Values** and **ValueMaps** and the property is mapped to the enumeration.</span></span>  
  
- <span data-ttu-id="56719-195">La strumentazione WMI utilizza il termine Singleton per descrivere una classe che può avere una sola istanza.</span><span class="sxs-lookup"><span data-stu-id="56719-195">The WMI uses the term singleton to describe a class that can have only one instance.</span></span> <span data-ttu-id="56719-196">Il costruttore senza parametri per una classe singleton, pertanto, inizializzerà la classe per l'unica istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="56719-196">Therefore, the parameterless constructor for a singleton class will initialize the class to the only instance of the class.</span></span>  
  
- <span data-ttu-id="56719-197">Le proprietà di una classe WMI possono essere oggetti.</span><span class="sxs-lookup"><span data-stu-id="56719-197">A WMI class can have properties that are objects.</span></span> <span data-ttu-id="56719-198">Quando si genera una classe fortemente tipizzata per questo tipo di classe WMI, valutare di generare classi fortemente tipizzate per i tipi delle proprietà oggetti incorporati.</span><span class="sxs-lookup"><span data-stu-id="56719-198">When you generate a strongly-typed class for this type of WMI class, you should consider generating strongly-typed classes for the types of the embedded object properties.</span></span> <span data-ttu-id="56719-199">Sarà così possibile eseguire un accesso fortemente tipizzato agli oggetti incorporati.</span><span class="sxs-lookup"><span data-stu-id="56719-199">This will allow you to access the embedded objects in a strongly-typed manner.</span></span> <span data-ttu-id="56719-200">Il codice generato potrebbe non essere in grado di individuare il tipo dell'oggetto incorporato.</span><span class="sxs-lookup"><span data-stu-id="56719-200">Note that the generated code might not be able to detect the type of the embedded object.</span></span> <span data-ttu-id="56719-201">In tal caso nel codice generato verrà creato un commento che notifica il problema.</span><span class="sxs-lookup"><span data-stu-id="56719-201">In this case, a comment will be created in the generated code to notify you of this issue.</span></span> <span data-ttu-id="56719-202">Sarà quindi possibile modificare il codice generato per tipizzare la proprietà sull'altra classe generata.</span><span class="sxs-lookup"><span data-stu-id="56719-202">You can then modify the generated code to type the property to the other generated class.</span></span>  
  
- <span data-ttu-id="56719-203">In WMI il valore dei dati del tipo di dati CIM_DATETIME può rappresentare una specifica data e ora o un intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="56719-203">In WMI, the data value of the CIM_DATETIME data type can represent either a specific date and time or a time interval.</span></span> <span data-ttu-id="56719-204">Se il valore dei dati rappresenta una data e un'ora, il tipo di dati nella classe generata è **DateTime**.</span><span class="sxs-lookup"><span data-stu-id="56719-204">If the data value represents a date and time, the data type in the generated class is **DateTime**.</span></span> <span data-ttu-id="56719-205">Se il valore dei dati rappresenta un intervallo di tempo, il tipo di dati nella classe generata è **TimeSpan**.</span><span class="sxs-lookup"><span data-stu-id="56719-205">If the data value represents a time interval, the data type in the generated class is **TimeSpan**.</span></span>  
  
 <span data-ttu-id="56719-206">In alternativa è possibile generare una classe fortemente tipizzata utilizzando l'estensione di gestione per Esplora server di Visual Studio .NET.</span><span class="sxs-lookup"><span data-stu-id="56719-206">You can alternately generate a strongly-typed class using the Server Explorer Management Extension in Visual Studio .NET.</span></span>  
  
 <span data-ttu-id="56719-207">Per altre informazioni su WMI, vedere l'argomento **Windows Management Instrumentation** (Strumentazione gestione Windows (WMI)) nella documentazione di Platform SDK.</span><span class="sxs-lookup"><span data-stu-id="56719-207">For more information about WMI, see the **Windows Management Instrumentation** topic in the Platform SDK documentation.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="56719-208">Esempi</span><span class="sxs-lookup"><span data-stu-id="56719-208">Examples</span></span>  
 <span data-ttu-id="56719-209">Il comando seguente genera una classe gestita in codice C# per la classe WMI **Win32_LogicalDisk** nello spazio dei nomi **Root\cimv2**.</span><span class="sxs-lookup"><span data-stu-id="56719-209">The following command generates a managed class in C# code for the **Win32_LogicalDisk** WMI class in the **Root\cimv2** namespace.</span></span> <span data-ttu-id="56719-210">Lo strumento scrive la classe gestita nel file di origine che si trova nel percorso c:\disk.cs dello spazio dei nomi **ROOT.CIMV2.Win32**.</span><span class="sxs-lookup"><span data-stu-id="56719-210">The tool writes the managed class to the source file at c:\disk.cs in the **ROOT.CIMV2.Win32** namespace.</span></span>  
  
```console  
mgmtclassgen Win32_LogicalDisk /n root\cimv2 /l CS /p c:\disk.cs  
```  
  
 <span data-ttu-id="56719-211">Nel codice di esempio riportato di seguito viene illustrato come utilizzare una classe generata a livello di programmazione.</span><span class="sxs-lookup"><span data-stu-id="56719-211">The following code example shows how to use a generated class programmatically.</span></span> <span data-ttu-id="56719-212">Innanzitutto viene enumerata un'istanza della classe e viene visualizzato il percorso.</span><span class="sxs-lookup"><span data-stu-id="56719-212">First, an instance of the class is enumerated and the path is printed.</span></span> <span data-ttu-id="56719-213">In seguito, un'istanza della classe generata da inizializzare viene creata con un'istanza di WMI.</span><span class="sxs-lookup"><span data-stu-id="56719-213">Next, an instance of the generated class to be initialized is created with an instance of WMI.</span></span> <span data-ttu-id="56719-214">`Process` è la classe generata per **Win32_Process** e `LogicalDisk` è la classe generata per **Win32_LogicalDisk** nello spazio dei nomi **Root\cimv2**.</span><span class="sxs-lookup"><span data-stu-id="56719-214">`Process` is the class generated for **Win32_Process** and `LogicalDisk` is the class generated for **Win32_LogicalDisk** in the **Root\cimv2** namespace.</span></span>  
  
```vb  
Imports System  
Imports System.Management  
Imports ROOT.CIMV2.Win32  
  
Public Class App
   Public Shared Sub Main()
      ' Enumerate instances of the Win32_process.  
      ' Print the Name property of the instance.  
      Dim ps As Process
      For Each ps In  Process.GetInstances()  
         Console.WriteLine(ps.Name)  
      Next ps  
  
      ' Initialize the instance of LogicalDisk with  
      ' the WMI instance pointing to logical drive d:.  
      Dim dskD As New LogicalDisk(New _  
         ManagementPath("win32_LogicalDisk.DeviceId=""d:"""))  
      Console.WriteLine(dskD.Caption)  
   End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Management;  
using ROOT.CIMV2.Win32;  
  
public class App  
{  
   public static void Main()  
   {  
      // Enumerate instances of the Win32_process.  
      // Print the Name property of the instance.  
      foreach(Process ps in Process.GetInstances())  
      {  
         Console.WriteLine(ps.Name);  
      }  
  
      // Initialize the instance of LogicalDisk with  
      // the WMI instance pointing to logical drive d:.  
      LogicalDisk dskD = new LogicalDisk(new ManagementPath(  
        "win32_LogicalDisk.DeviceId=\"d:\""));  
      Console.WriteLine(dskD.Caption);  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="56719-215">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56719-215">See also</span></span>

- <xref:System.Management>
- <xref:System.Management.ManagementClass.GetStronglyTypedClassCode%2A?displayProperty=nameWithType>
- <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>
- [<span data-ttu-id="56719-216">Strumenti</span><span class="sxs-lookup"><span data-stu-id="56719-216">Tools</span></span>](index.md)
- [<span data-ttu-id="56719-217">Prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="56719-217">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
