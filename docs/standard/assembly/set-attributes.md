---
title: Impostare gli attributi dell'assembly
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], attributes
- assembly binding, attributes
- assembly manifest, attributes
ms.assetid: 36a98a81-b5b5-4c19-912a-11f91eff7f4e
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 0e4e2e595ed4f95511bd23ab0ed00139f71b2c8b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73740477"
---
# <a name="set-assembly-attributes"></a><span data-ttu-id="a1b08-102">Impostare gli attributi dell'assembly</span><span class="sxs-lookup"><span data-stu-id="a1b08-102">Set assembly attributes</span></span>

<span data-ttu-id="a1b08-103">Gli attributi dell'assembly sono valori che forniscono informazioni relative a un assembly.</span><span class="sxs-lookup"><span data-stu-id="a1b08-103">Assembly attributes are values that provide information about an assembly.</span></span> <span data-ttu-id="a1b08-104">Tali attributi sono suddivisi nei seguenti gruppi di informazioni:</span><span class="sxs-lookup"><span data-stu-id="a1b08-104">The attributes are divided into the following sets of information:</span></span>

- <span data-ttu-id="a1b08-105">Attributi relativi all'identità dell'assembly</span><span class="sxs-lookup"><span data-stu-id="a1b08-105">Assembly identity attributes</span></span>

- <span data-ttu-id="a1b08-106">Attributi informativi</span><span class="sxs-lookup"><span data-stu-id="a1b08-106">Informational attributes</span></span>

- <span data-ttu-id="a1b08-107">Attributi relativi al manifesto dell'assembly</span><span class="sxs-lookup"><span data-stu-id="a1b08-107">Assembly manifest attributes</span></span>

- <span data-ttu-id="a1b08-108">Attributi relativi al nome sicuro</span><span class="sxs-lookup"><span data-stu-id="a1b08-108">Strong name attributes</span></span>

## <a name="assembly-identity-attributes"></a><span data-ttu-id="a1b08-109">Attributi relativi all'identità dell'assembly</span><span class="sxs-lookup"><span data-stu-id="a1b08-109">Assembly identity attributes</span></span>

<span data-ttu-id="a1b08-110">Tre attributi, insieme a un nome sicuro (se disponibile), consentono di determinare l'identità di un assembly: il nome, la versione e le impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="a1b08-110">Three attributes, together with a strong name (if applicable), determine the identity of an assembly: name, version, and culture.</span></span> <span data-ttu-id="a1b08-111">Il nome completo dell'assembly è costituito da questi attributi, che risultano necessari per creare riferimenti all'assembly nel codice.</span><span class="sxs-lookup"><span data-stu-id="a1b08-111">These attributes form the full name of the assembly and are required when referencing the assembly in code.</span></span> <span data-ttu-id="a1b08-112">È possibile usare gli attributi per impostare la versione e le impostazioni cultura di un assembly.</span><span class="sxs-lookup"><span data-stu-id="a1b08-112">You can use attributes to set an assembly's version and culture.</span></span> <span data-ttu-id="a1b08-113">Il valore relativo al nome viene impostato dal compilatore o da [Assembly Linker (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) quando l'assembly viene creato ed è basato sul file contenente il manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="a1b08-113">The compiler or the [Assembly Linker (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) sets the name value when the assembly is created, based on the file containing the assembly manifest.</span></span>

<span data-ttu-id="a1b08-114">Nella tabella seguente vengono descritti gli attributi relativi alla versione e alle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="a1b08-114">The following table describes the version and culture attributes.</span></span>

|<span data-ttu-id="a1b08-115">Attributi relativi all'identità dell'assembly</span><span class="sxs-lookup"><span data-stu-id="a1b08-115">Assembly identity attribute</span></span>|<span data-ttu-id="a1b08-116">Description</span><span class="sxs-lookup"><span data-stu-id="a1b08-116">Description</span></span>|
|---------------------------------|-----------------|
|<xref:System.Reflection.AssemblyCultureAttribute>|<span data-ttu-id="a1b08-117">Campo elenco in cui vengono indicate le impostazioni cultura supportate dall'assembly.</span><span class="sxs-lookup"><span data-stu-id="a1b08-117">Enumerated field indicating the culture that the assembly supports.</span></span> <span data-ttu-id="a1b08-118">È possibile specificare anche l'indipendenza dalle impostazioni cultura per l'assembly, indicando che nell'assembly sono presenti le risorse per le impostazioni cultura predefinite.</span><span class="sxs-lookup"><span data-stu-id="a1b08-118">An assembly can also specify culture independence, indicating that it contains the resources for the default culture.</span></span> <span data-ttu-id="a1b08-119">**Nota:** tutti gli assembly il cui attributo "Culture" non è impostato su Null vengono considerati dal runtime come assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="a1b08-119">**Note:**  The runtime treats any assembly that does not have the culture attribute set to null as a satellite assembly.</span></span> <span data-ttu-id="a1b08-120">e sono soggetti alle regole di associazione degli assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="a1b08-120">Such assemblies are subject to satellite assembly binding rules.</span></span> <span data-ttu-id="a1b08-121">Per ulteriori informazioni, vedere [come il runtime individua gli assembly](../../framework/deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="a1b08-121">For more information, see [How the runtime locates assemblies](../../framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>|
|<xref:System.Reflection.AssemblyFlagsAttribute>|<span data-ttu-id="a1b08-122">Valore che consente di impostare gli attributi relativi all'assembly, indicando ad esempio se è consentita l'esecuzione affiancata di più versioni.</span><span class="sxs-lookup"><span data-stu-id="a1b08-122">Value that sets assembly attributes, such as whether the assembly can be run side by side.</span></span>|
|<xref:System.Reflection.AssemblyVersionAttribute>|<span data-ttu-id="a1b08-123">Valore numerico in formato *principale*.*secondario*.*build*.*revisione* (ad esempio, 2.4.0.0).</span><span class="sxs-lookup"><span data-stu-id="a1b08-123">Numeric value in the format *major*.*minor*.*build*.*revision* (for example, 2.4.0.0).</span></span> <span data-ttu-id="a1b08-124">Questo valore viene usato da Common Language Runtime per eseguire operazioni di associazione in assembly con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="a1b08-124">The common language runtime uses this value to perform binding operations in strong-named assemblies.</span></span> <span data-ttu-id="a1b08-125">**Nota:**  Se l' <xref:System.Reflection.AssemblyInformationalVersionAttribute> attributo non viene applicato a un assembly, il numero di versione specificato dall' <xref:System.Reflection.AssemblyVersionAttribute> attributo viene usato dalle proprietà <xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=nameWithType>, <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType>e <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="a1b08-125">**Note:**  If the <xref:System.Reflection.AssemblyInformationalVersionAttribute> attribute is not applied to an assembly, the version number specified by the <xref:System.Reflection.AssemblyVersionAttribute> attribute is used by the <xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=nameWithType>, <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType>, and <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=nameWithType> properties.</span></span>|

<span data-ttu-id="a1b08-126">Nel seguente esempio di codice viene mostrato come applicare a un assembly gli attributi relativi alla versione e alle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="a1b08-126">The following code example shows how to apply the version and culture attributes to an assembly.</span></span>

```cpp
// Set version number for the assembly.
[assembly:AssemblyVersionAttribute("4.3.2.1")];
// Set culture as German.
[assembly:AssemblyCultureAttribute("de")];
```

```csharp
// Set version number for the assembly.
[assembly:AssemblyVersionAttribute("4.3.2.1")]
// Set culture as German.
[assembly:AssemblyCultureAttribute("de")]
```

```vb
' Set version number for the assembly.
<Assembly:AssemblyVersionAttribute("4.3.2.1")>
' Set culture as German.
<Assembly:AssemblyCultureAttribute("de")>
```

## <a name="informational-attributes"></a><span data-ttu-id="a1b08-127">Attributi informativi</span><span class="sxs-lookup"><span data-stu-id="a1b08-127">Informational attributes</span></span>

<span data-ttu-id="a1b08-128">Gli attributi informativi consentono di fornire informazioni aggiuntive relative alla società o al prodotto per un assembly.</span><span class="sxs-lookup"><span data-stu-id="a1b08-128">You can use informational attributes to provide additional company or product information for an assembly.</span></span> <span data-ttu-id="a1b08-129">Nella tabella seguente vengono descritti gli attributi informativi che è possibile applicare a un assembly.</span><span class="sxs-lookup"><span data-stu-id="a1b08-129">The following table describes the informational attributes you can apply to an assembly.</span></span>

|<span data-ttu-id="a1b08-130">Attributo informativo</span><span class="sxs-lookup"><span data-stu-id="a1b08-130">Informational attribute</span></span>|<span data-ttu-id="a1b08-131">Description</span><span class="sxs-lookup"><span data-stu-id="a1b08-131">Description</span></span>|
|-----------------------------|-----------------|
|<xref:System.Reflection.AssemblyCompanyAttribute>|<span data-ttu-id="a1b08-132">Valore stringa in cui viene specificato un nome di società.</span><span class="sxs-lookup"><span data-stu-id="a1b08-132">String value specifying a company name.</span></span>|
|<xref:System.Reflection.AssemblyCopyrightAttribute>|<span data-ttu-id="a1b08-133">Valore stringa in cui vengono specificate informazioni relative al copyright.</span><span class="sxs-lookup"><span data-stu-id="a1b08-133">String value specifying copyright information.</span></span>|
|<xref:System.Reflection.AssemblyFileVersionAttribute>|<span data-ttu-id="a1b08-134">Valore stringa in cui viene specificato il numero di versione del file Win32.</span><span class="sxs-lookup"><span data-stu-id="a1b08-134">String value specifying the Win32 file version number.</span></span> <span data-ttu-id="a1b08-135">L'impostazione predefinita è solitamente la versione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="a1b08-135">This normally defaults to the assembly version.</span></span>|
|<xref:System.Reflection.AssemblyInformationalVersionAttribute>|<span data-ttu-id="a1b08-136">Valore stringa in cui vengono specificate informazioni relative alla versione non usate da Common Language Runtime, quale il numero di versione del prodotto completo.</span><span class="sxs-lookup"><span data-stu-id="a1b08-136">String value specifying version information that is not used by the common language runtime, such as a full product version number.</span></span> <span data-ttu-id="a1b08-137">**Nota:** se questo attributo viene applicato a un assembly, è possibile ottenere la stringa specificata in fase di esecuzione tramite la proprietà <xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a1b08-137">**Note:**  If this attribute is applied to an assembly, the string it specifies can be obtained at run time by using the <xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="a1b08-138">La stringa viene usata anche nel percorso e nella chiave del Registro di sistema specificati dalle proprietà <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType> e <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a1b08-138">The string is also used in the path and registry key provided by the <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=nameWithType> properties.</span></span>|
|<xref:System.Reflection.AssemblyProductAttribute>|<span data-ttu-id="a1b08-139">Valore stringa in cui vengono specificate informazioni relative al prodotto.</span><span class="sxs-lookup"><span data-stu-id="a1b08-139">String value specifying product information.</span></span>|
|<xref:System.Reflection.AssemblyTrademarkAttribute>|<span data-ttu-id="a1b08-140">Valore stringa in cui vengono specificate informazioni relative al marchio registrato.</span><span class="sxs-lookup"><span data-stu-id="a1b08-140">String value specifying trademark information.</span></span>|

<span data-ttu-id="a1b08-141">È possibile visualizzare questi attributi nella pagina delle proprietà di Windows o sostituirli usando l'opzione del compilatore **/win32res** per specificare un file di risorsa Win32 personalizzato.</span><span class="sxs-lookup"><span data-stu-id="a1b08-141">These attributes can appear on the Windows Properties page of the assembly, or they can be overridden using the **/win32res** compiler option to specify your own Win32 resource file.</span></span>

## <a name="assembly-manifest-attributes"></a><span data-ttu-id="a1b08-142">Attributi relativi al manifesto dell'assembly</span><span class="sxs-lookup"><span data-stu-id="a1b08-142">Assembly manifest attributes</span></span>

<span data-ttu-id="a1b08-143">Gli attributi relativi al manifesto dell'assembly consentono di fornire informazioni nel manifesto dell'assembly, inclusi il titolo, la descrizione, l'alias predefinito e la configurazione.</span><span class="sxs-lookup"><span data-stu-id="a1b08-143">You can use assembly manifest attributes to provide information in the assembly manifest, including title, description, the default alias, and configuration.</span></span> <span data-ttu-id="a1b08-144">Nella tabella seguente vengono descritti gli attributi relativi al manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="a1b08-144">The following table describes the assembly manifest attributes.</span></span>

|<span data-ttu-id="a1b08-145">Attributo relativo al manifesto dell'assembly</span><span class="sxs-lookup"><span data-stu-id="a1b08-145">Assembly manifest attribute</span></span>|<span data-ttu-id="a1b08-146">Description</span><span class="sxs-lookup"><span data-stu-id="a1b08-146">Description</span></span>|
|---------------------------------|-----------------|
|<xref:System.Reflection.AssemblyConfigurationAttribute>|<span data-ttu-id="a1b08-147">Valore stringa che indica la configurazione dell'assembly, ad esempio finale o di debug.</span><span class="sxs-lookup"><span data-stu-id="a1b08-147">String value indicating the configuration of the assembly, such as Retail or Debug.</span></span> <span data-ttu-id="a1b08-148">Questo valore non viene usato da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="a1b08-148">The runtime does not use this value.</span></span>|
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|<span data-ttu-id="a1b08-149">Valore stringa in cui viene specificato l'alias predefinito che verrà usato dagli assembly contenenti riferimenti all'assembly corrente.</span><span class="sxs-lookup"><span data-stu-id="a1b08-149">String value specifying a default alias to be used by referencing assemblies.</span></span> <span data-ttu-id="a1b08-150">Questo valore consente di fornire un nome descrittivo nel caso in cui il nome dell'assembly non sia descrittivo, ma corrisponda ad esempio a un valore GUID.</span><span class="sxs-lookup"><span data-stu-id="a1b08-150">This value provides a friendly name when the name of the assembly itself is not friendly (such as a GUID value).</span></span> <span data-ttu-id="a1b08-151">È inoltre possibile usare questo valore come forma abbreviata del nome completo dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="a1b08-151">This value can also be used as a short form of the full assembly name.</span></span>|
|<xref:System.Reflection.AssemblyDescriptionAttribute>|<span data-ttu-id="a1b08-152">Valore stringa in cui viene specificata una breve descrizione che riassume la natura e lo scopo dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="a1b08-152">String value specifying a short description that summarizes the nature and purpose of the assembly.</span></span>|
|<xref:System.Reflection.AssemblyTitleAttribute>|<span data-ttu-id="a1b08-153">Valore stringa in cui viene specificato un nome descrittivo per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="a1b08-153">String value specifying a friendly name for the assembly.</span></span> <span data-ttu-id="a1b08-154">Ad esempio, un assembly denominato *comdlg* potrebbe avere il titolo Microsoft Common Dialog Control.</span><span class="sxs-lookup"><span data-stu-id="a1b08-154">For example, an assembly named *comdlg* might have the title Microsoft Common Dialog Control.</span></span>|

## <a name="strong-name-attributes"></a><span data-ttu-id="a1b08-155">Attributi relativi al nome sicuro</span><span class="sxs-lookup"><span data-stu-id="a1b08-155">Strong name attributes</span></span>

<span data-ttu-id="a1b08-156">Gli attributi relativi al nome sicuro consentono di impostare un nome sicuro per un assembly.</span><span class="sxs-lookup"><span data-stu-id="a1b08-156">You can use strong name attributes to set a strong name for an assembly.</span></span> <span data-ttu-id="a1b08-157">Nella tabella seguente vengono descritti gli attributi relativi al nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="a1b08-157">The following table describes the strong name attributes.</span></span>

|<span data-ttu-id="a1b08-158">Attributo nome sicuro</span><span class="sxs-lookup"><span data-stu-id="a1b08-158">Strong name attribute</span></span>|<span data-ttu-id="a1b08-159">Description</span><span class="sxs-lookup"><span data-stu-id="a1b08-159">Description</span></span>|
|----------------------------|-----------------|
|<xref:System.Reflection.AssemblyDelaySignAttribute>|<span data-ttu-id="a1b08-160">Valore booleano che indica che viene usato il ritardo della firma.</span><span class="sxs-lookup"><span data-stu-id="a1b08-160">Boolean value indicating that delay signing is being used.</span></span>|
|<xref:System.Reflection.AssemblyKeyFileAttribute>|<span data-ttu-id="a1b08-161">Valore stringa che indica il nome del file contenente la chiave pubblica (se si usa il ritardo della firma) o la chiave pubblica e privata passate come parametro al costruttore di questo attributo.</span><span class="sxs-lookup"><span data-stu-id="a1b08-161">String value indicating the name of the file that contains either the public key (if using delay signing) or both the public and private keys passed as a parameter to the constructor of this attribute.</span></span> <span data-ttu-id="a1b08-162">Si noti che il nome del file è relativo al percorso del file di output ( *exe* o *dll*), non al percorso del file di origine.</span><span class="sxs-lookup"><span data-stu-id="a1b08-162">Note that the file name is relative to the output file path (the *.exe* or *.dll*), not the source file path.</span></span>|
|<xref:System.Reflection.AssemblyKeyNameAttribute>|<span data-ttu-id="a1b08-163">Indica il contenitore di chiave contenente la coppia di chiavi passata come parametro al costruttore dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="a1b08-163">Indicates the key container that contains the key pair passed as a parameter to the constructor of this attribute.</span></span>|

<span data-ttu-id="a1b08-164">Nell'esempio di codice seguente vengono illustrati gli attributi da applicare quando si utilizza la firma ritardata per creare un assembly con nome sicuro con un file di chiave pubblica denominato *myKey. snk*.</span><span class="sxs-lookup"><span data-stu-id="a1b08-164">The following code example shows the attributes to apply when using delay signing to create a strong-named assembly with a public key file called *myKey.snk*.</span></span>

```cpp
[assembly:AssemblyKeyFileAttribute("myKey.snk")];
[assembly:AssemblyDelaySignAttribute(true)];
```

```csharp
[assembly:AssemblyKeyFileAttribute("myKey.snk")]
[assembly:AssemblyDelaySignAttribute(true)]
```

```vb
<Assembly:AssemblyKeyFileAttribute("myKey.snk")>
<Assembly:AssemblyDelaySignAttribute(True)>
```

## <a name="see-also"></a><span data-ttu-id="a1b08-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1b08-165">See also</span></span>

- [<span data-ttu-id="a1b08-166">Creare assembly</span><span class="sxs-lookup"><span data-stu-id="a1b08-166">Create assemblies</span></span>](create.md)
