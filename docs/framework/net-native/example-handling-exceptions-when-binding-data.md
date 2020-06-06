---
title: 'Esempio: Gestione delle eccezioni durante il data binding'
ms.date: 03/30/2017
ms.assetid: bd63ed96-9853-46dc-ade5-7bd1b0f39110
ms.openlocfilehash: b774d1bce4f4d1c03258ed44b27d3871e7c5275f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79181027"
---
# <a name="example-handling-exceptions-when-binding-data"></a><span data-ttu-id="27787-102">Esempio: Gestione delle eccezioni durante il data binding</span><span class="sxs-lookup"><span data-stu-id="27787-102">Example: Handling Exceptions When Binding Data</span></span>
> [!NOTE]
> <span data-ttu-id="27787-103">In questo argomento si fa riferimento a .NET Native Developer Preview, ovvero la versione preliminare del software,</span><span class="sxs-lookup"><span data-stu-id="27787-103">This topic refers to the .NET Native Developer Preview, which is pre-release software.</span></span> <span data-ttu-id="27787-104">che è possibile scaricare dal [sito Web di Microsoft Connect](https://go.microsoft.com/fwlink/?LinkId=394611) (è necessaria la registrazione).</span><span class="sxs-lookup"><span data-stu-id="27787-104">You can download the preview from the [Microsoft Connect website](https://go.microsoft.com/fwlink/?LinkId=394611) (requires registration).</span></span>  
  
 <span data-ttu-id="27787-105">Nell'esempio seguente viene illustrato come risolvere un'eccezione [MissingMetadataException](missingmetadataexception-class-net-native.md) generata quando un'app compilata con la catena di strumenti .NET native tenta di associare i dati.</span><span class="sxs-lookup"><span data-stu-id="27787-105">The following example shows how to resolve a [MissingMetadataException](missingmetadataexception-class-net-native.md) exception that is thrown when an app compiled with the .NET Native tool chain tries to bind data.</span></span> <span data-ttu-id="27787-106">Queste sono le informazioni sull'eccezione:</span><span class="sxs-lookup"><span data-stu-id="27787-106">Here’s the exception information:</span></span>  
  
```output
This operation cannot be carried out as metadata for the following type was removed for performance reasons:
App.ViewModels.MainPageVM  
```  
  
 <span data-ttu-id="27787-107">Questo è lo stack di chiamate associato:</span><span class="sxs-lookup"><span data-stu-id="27787-107">Here's the associated call stack:</span></span>  
  
```output
Reflection::Execution::ReflectionDomainSetupImplementation.CreateNonInvokabilityException+0x238  
Reflection::Core::ReflectionDomain.CreateNonInvokabilityException+0x2e  
Reflection::Core::Execution::ExecutionEnvironment.+0x316  
System::Reflection::Runtime::PropertyInfos::RuntimePropertyInfo.GetValue+0x1cb  
System::Reflection::PropertyInfo.GetValue+0x22  
System::Runtime::InteropServices::WindowsRuntime::CustomPropertyImpl.GetValue+0x42  
App!$66_Interop::McgNative.Func_IInspectable_IInspectable+0x158  
App!$66_Interop::McgNative::__vtable_Windows_UI_Xaml_Data__ICustomProperty.GetValue__STUB+0x46  
Windows_UI_Xaml!DirectUI::PropertyProviderPropertyAccess::GetValue+0x3f
Windows_UI_Xaml!DirectUI::PropertyAccessPathStep::GetValue+0x31
Windows_UI_Xaml!DirectUI::PropertyPathListener::ConnectPathStep+0x113  
```  
  
## <a name="what-was-the-app-doing"></a><span data-ttu-id="27787-108">Che cosa stava eseguendo l'app?</span><span class="sxs-lookup"><span data-stu-id="27787-108">What was the app doing?</span></span>  
 <span data-ttu-id="27787-109">Alla base dello stack, i frame dello <xref:Windows.UI.Xaml?displayProperty=nameWithType> spazio dei nomi indicano che il motore di rendering XAML era in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="27787-109">At the base of the stack, frames from the <xref:Windows.UI.Xaml?displayProperty=nameWithType> namespace indicate that the XAML rendering engine was running.</span></span>   <span data-ttu-id="27787-110">L'uso del metodo <xref:System.Reflection.PropertyInfo.GetValue%2A?displayProperty=nameWithType> indica una ricerca basata su reflection del valore di una proprietà sul tipo di cui sono stati rimossi i metadati.</span><span class="sxs-lookup"><span data-stu-id="27787-110">The use of the <xref:System.Reflection.PropertyInfo.GetValue%2A?displayProperty=nameWithType> method indicates a reflection-based lookup of a property’s value on the type whose metadata was removed.</span></span>  
  
 <span data-ttu-id="27787-111">Il primo passaggio per la fornitura di una direttiva di metadati consiste nell'aggiunta di metadati `serialize` per il tipo che ne rende accessibili le proprietà:</span><span class="sxs-lookup"><span data-stu-id="27787-111">The first step in providing a metadata directive would be to add `serialize` metadata for the type so that its properties are all accessible:</span></span>  
  
```xml  
<Type Name="App.ViewModels.MainPageVM" Serialize="Required Public" />  
```  
  
## <a name="is-this-an-isolated-case"></a><span data-ttu-id="27787-112">Si tratta di un caso isolato?</span><span class="sxs-lookup"><span data-stu-id="27787-112">Is this an isolated case?</span></span>  
 <span data-ttu-id="27787-113">In questo scenario, se il data binding contiene metadati incompleti per `ViewModel`, potrebbe contenerne anche per altri.</span><span class="sxs-lookup"><span data-stu-id="27787-113">In this scenario, if data binding has incomplete metadata for one `ViewModel`, it may for others, too.</span></span>  <span data-ttu-id="27787-114">Se il codice è strutturato in modo che i modelli di visualizzazione dell'app siano tutti nello spazio dei nomi `App.ViewModels`, è possibile usare una direttiva di runtime più generale:</span><span class="sxs-lookup"><span data-stu-id="27787-114">If the code is structured in a way that the app’s view models are all in the `App.ViewModels` namespace, you could use a more general runtime directive:</span></span>  
  
```xml  
<Namespace Name="App.ViewModels " Serialize="Required Public" />  
```  
  
## <a name="could-the-code-be-rewritten-to-not-use-reflection"></a><span data-ttu-id="27787-115">Il codice può essere riscritto per escludere l'uso della reflection?</span><span class="sxs-lookup"><span data-stu-id="27787-115">Could the code be rewritten to not use reflection?</span></span>  
 <span data-ttu-id="27787-116">Il data binding ha un elevato livello di reflection, pertanto la modifica del codice per impedire la reflection non è consentita.</span><span class="sxs-lookup"><span data-stu-id="27787-116">Because data binding is reflection-intensive, changing the code to avoid reflection isn’t feasible.</span></span>  
  
 <span data-ttu-id="27787-117">Tuttavia, sono disponibili dei metodi per specificare `ViewModel` nella pagina XAML in modo che la catena di strumenti possa associare le associazioni di proprietà al tipo corretto durante la compilazione e mantenere i metadati senza usare una direttiva di runtime.</span><span class="sxs-lookup"><span data-stu-id="27787-117">However, there are ways to specify the `ViewModel` to the XAML page so that the tool chain can associate property bindings with the correct type at compile time and keep the metadata without using a runtime directive.</span></span>  <span data-ttu-id="27787-118">Ad esempio, è possibile applicare l' <xref:Windows.UI.Xaml.Data.BindableAttribute?displayProperty=nameWithType> attributo alle proprietà.</span><span class="sxs-lookup"><span data-stu-id="27787-118">For example, you could apply the <xref:Windows.UI.Xaml.Data.BindableAttribute?displayProperty=nameWithType> attribute on properties.</span></span> <span data-ttu-id="27787-119">In questo modo il compilatore XAML genera le informazioni di ricerca necessarie ed evita la richiesta di una direttiva di runtime nel file Default.rd.xml.</span><span class="sxs-lookup"><span data-stu-id="27787-119">This causes the XAML compiler to generate the required lookup information and avoids requiring a runtime directive in the Default.rd.xml file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27787-120">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="27787-120">See also</span></span>

- [<span data-ttu-id="27787-121">Per iniziare</span><span class="sxs-lookup"><span data-stu-id="27787-121">Getting Started</span></span>](getting-started-with-net-native.md)
- [<span data-ttu-id="27787-122">Esempio: Risoluzione dei problemi di programmazione dinamica</span><span class="sxs-lookup"><span data-stu-id="27787-122">Example: Troubleshooting Dynamic Programming</span></span>](example-troubleshooting-dynamic-programming.md)
