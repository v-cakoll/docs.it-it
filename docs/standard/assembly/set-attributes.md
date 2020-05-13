---
title: Impostare gli attributi dell'assembly
description: È possibile impostare gli attributi di assembly per un assembly .NET, inclusi l'identità dell'assembly, l'informativa, il manifesto dell'assembly e gli attributi del nome sicuro.
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
ms.openlocfilehash: e3a077dcd1b62a4676a3ac6492a90e38c548e41b
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378640"
---
# <a name="set-assembly-attributes"></a>Impostare gli attributi dell'assembly

Gli attributi dell'assembly sono valori che forniscono informazioni relative a un assembly. Tali attributi sono suddivisi nei seguenti gruppi di informazioni:

- Attributi relativi all'identità dell'assembly

- Attributi informativi

- Attributi relativi al manifesto dell'assembly

- Attributi relativi al nome sicuro

## <a name="assembly-identity-attributes"></a>Attributi relativi all'identità dell'assembly

Tre attributi, insieme a un nome sicuro (se disponibile), consentono di determinare l'identità di un assembly: il nome, la versione e le impostazioni cultura. Il nome completo dell'assembly è costituito da questi attributi, che risultano necessari per creare riferimenti all'assembly nel codice. È possibile usare gli attributi per impostare la versione e le impostazioni cultura di un assembly. Il valore relativo al nome viene impostato dal compilatore o da [Assembly Linker (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) quando l'assembly viene creato ed è basato sul file contenente il manifesto dell'assembly.

Nella tabella seguente vengono descritti gli attributi relativi alla versione e alle impostazioni cultura.

|Attributi relativi all'identità dell'assembly|Description|
|---------------------------------|-----------------|
|<xref:System.Reflection.AssemblyCultureAttribute>|Campo elenco in cui vengono indicate le impostazioni cultura supportate dall'assembly. È possibile specificare anche l'indipendenza dalle impostazioni cultura per l'assembly, indicando che nell'assembly sono presenti le risorse per le impostazioni cultura predefinite. **Nota:** tutti gli assembly il cui attributo "Culture" non è impostato su Null vengono considerati dal runtime come assembly satellite. e sono soggetti alle regole di associazione degli assembly satellite. Per ulteriori informazioni, vedere [come il runtime individua gli assembly](../../framework/deployment/how-the-runtime-locates-assemblies.md).|
|<xref:System.Reflection.AssemblyFlagsAttribute>|Valore che consente di impostare gli attributi relativi all'assembly, indicando ad esempio se è consentita l'esecuzione affiancata di più versioni.|
|<xref:System.Reflection.AssemblyVersionAttribute>|Valore numerico in formato *principale*.*secondario*.*build*.*revisione* (ad esempio, 2.4.0.0). Questo valore viene usato da Common Language Runtime per eseguire operazioni di associazione in assembly con nome sicuro. **Nota:**  Se l' <xref:System.Reflection.AssemblyInformationalVersionAttribute> attributo non viene applicato a un assembly, il numero di versione specificato dall' <xref:System.Reflection.AssemblyVersionAttribute> attributo viene usato dalle <xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=nameWithType> proprietà, <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType> e <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=nameWithType> .|

Nel seguente esempio di codice viene mostrato come applicare a un assembly gli attributi relativi alla versione e alle impostazioni cultura.

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

## <a name="informational-attributes"></a>Attributi informativi

Gli attributi informativi consentono di fornire informazioni aggiuntive relative alla società o al prodotto per un assembly. Nella tabella seguente vengono descritti gli attributi informativi che è possibile applicare a un assembly.

|Attributo informativo|Description|
|-----------------------------|-----------------|
|<xref:System.Reflection.AssemblyCompanyAttribute>|Valore stringa in cui viene specificato un nome di società.|
|<xref:System.Reflection.AssemblyCopyrightAttribute>|Valore stringa in cui vengono specificate informazioni relative al copyright.|
|<xref:System.Reflection.AssemblyFileVersionAttribute>|Valore stringa in cui viene specificato il numero di versione del file Win32. L'impostazione predefinita è solitamente la versione dell'assembly.|
|<xref:System.Reflection.AssemblyInformationalVersionAttribute>|Valore stringa in cui vengono specificate informazioni relative alla versione non usate da Common Language Runtime, quale il numero di versione del prodotto completo. **Nota:** se questo attributo viene applicato a un assembly, è possibile ottenere la stringa specificata in fase di esecuzione tramite la proprietà <xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=nameWithType>. La stringa viene usata anche nel percorso e nella chiave del Registro di sistema specificati dalle proprietà <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType> e <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=nameWithType>.|
|<xref:System.Reflection.AssemblyProductAttribute>|Valore stringa in cui vengono specificate informazioni relative al prodotto.|
|<xref:System.Reflection.AssemblyTrademarkAttribute>|Valore stringa in cui vengono specificate informazioni relative al marchio registrato.|

È possibile visualizzare questi attributi nella pagina delle proprietà di Windows o sostituirli usando l'opzione del compilatore **/win32res** per specificare un file di risorsa Win32 personalizzato.

## <a name="assembly-manifest-attributes"></a>Attributi relativi al manifesto dell'assembly

Gli attributi relativi al manifesto dell'assembly consentono di fornire informazioni nel manifesto dell'assembly, inclusi il titolo, la descrizione, l'alias predefinito e la configurazione. Nella tabella seguente vengono descritti gli attributi relativi al manifesto dell'assembly.

|Attributo relativo al manifesto dell'assembly|Description|
|---------------------------------|-----------------|
|<xref:System.Reflection.AssemblyConfigurationAttribute>|Valore stringa che indica la configurazione dell'assembly, ad esempio finale o di debug. Questo valore non viene usato da Common Language Runtime.|
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|Valore stringa in cui viene specificato l'alias predefinito che verrà usato dagli assembly contenenti riferimenti all'assembly corrente. Questo valore consente di fornire un nome descrittivo nel caso in cui il nome dell'assembly non sia descrittivo, ma corrisponda ad esempio a un valore GUID. È inoltre possibile usare questo valore come forma abbreviata del nome completo dell'assembly.|
|<xref:System.Reflection.AssemblyDescriptionAttribute>|Valore stringa in cui viene specificata una breve descrizione che riassume la natura e lo scopo dell'assembly.|
|<xref:System.Reflection.AssemblyTitleAttribute>|Valore stringa in cui viene specificato un nome descrittivo per l'assembly. Ad esempio, un assembly denominato *comdlg* potrebbe avere il titolo Microsoft Common Dialog Control.|

## <a name="strong-name-attributes"></a>Attributi relativi al nome sicuro

Gli attributi relativi al nome sicuro consentono di impostare un nome sicuro per un assembly. Nella tabella seguente vengono descritti gli attributi relativi al nome sicuro.

|Attributo nome sicuro|Description|
|----------------------------|-----------------|
|<xref:System.Reflection.AssemblyDelaySignAttribute>|Valore booleano che indica che viene usato il ritardo della firma.|
|<xref:System.Reflection.AssemblyKeyFileAttribute>|Valore stringa che indica il nome del file contenente la chiave pubblica (se si usa il ritardo della firma) o la chiave pubblica e privata passate come parametro al costruttore di questo attributo. Si noti che il nome del file è relativo al percorso del file di output ( *exe* o *dll*), non al percorso del file di origine.|
|<xref:System.Reflection.AssemblyKeyNameAttribute>|Indica il contenitore di chiave contenente la coppia di chiavi passata come parametro al costruttore dell'attributo.|

Nell'esempio di codice seguente vengono illustrati gli attributi da applicare quando si utilizza la firma ritardata per creare un assembly con nome sicuro con un file di chiave pubblica denominato *myKey. snk*.

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

## <a name="see-also"></a>Vedere anche

- [Creare assembly](create.md)
