---
title: 'Esempio: gestione delle eccezioni durante il data binding'
ms.date: 03/30/2017
ms.assetid: bd63ed96-9853-46dc-ade5-7bd1b0f39110
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 89e7a0929bd5f07c5a1986d885984332d692d3a9
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43867117"
---
# <a name="example-handling-exceptions-when-binding-data"></a><span data-ttu-id="6e3fe-102">Esempio: gestione delle eccezioni durante il data binding</span><span class="sxs-lookup"><span data-stu-id="6e3fe-102">Example: Handling Exceptions When Binding Data</span></span>
> [!NOTE]
>  <span data-ttu-id="6e3fe-103">In questo argomento si fa riferimento a .NET Native Developer Preview, ovvero la versione preliminare del software,</span><span class="sxs-lookup"><span data-stu-id="6e3fe-103">This topic refers to the .NET Native Developer Preview, which is pre-release software.</span></span> <span data-ttu-id="6e3fe-104">che è possibile scaricare dal [sito Web di Microsoft Connect](https://go.microsoft.com/fwlink/?LinkId=394611) (è necessaria la registrazione).</span><span class="sxs-lookup"><span data-stu-id="6e3fe-104">You can download the preview from the [Microsoft Connect website](https://go.microsoft.com/fwlink/?LinkId=394611) (requires registration).</span></span>  
  
 <span data-ttu-id="6e3fe-105">L'esempio seguente illustra come risolvere un'eccezione [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) generata quando un'app compilata con la catena di strumenti [!INCLUDE[net_native](../../../includes/net-native-md.md)] prova ad associare i dati.</span><span class="sxs-lookup"><span data-stu-id="6e3fe-105">The following example shows how to resolve a [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) exception that is thrown when an app compiled with the [!INCLUDE[net_native](../../../includes/net-native-md.md)] tool chain tries to bind data.</span></span> <span data-ttu-id="6e3fe-106">Queste sono le informazioni sull'eccezione:</span><span class="sxs-lookup"><span data-stu-id="6e3fe-106">Here’s the exception information:</span></span>  
  
```  
This operation cannot be carried out as metadata for the following type was removed for performance reasons:   
App.ViewModels.MainPageVM  
```  
  
 <span data-ttu-id="6e3fe-107">Questo è lo stack di chiamate associato:</span><span class="sxs-lookup"><span data-stu-id="6e3fe-107">Here's the associated call stack:</span></span>  
  
```  
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
  
## <a name="what-was-the-app-doing"></a><span data-ttu-id="6e3fe-108">Che cosa stava eseguendo l'app?</span><span class="sxs-lookup"><span data-stu-id="6e3fe-108">What was the app doing?</span></span>  
 <span data-ttu-id="6e3fe-109">Alla base dello stack, i frame dello spazio dei nomi [Windows.UI.Xaml](https://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.aspx) indicano che il motore di rendering XAML era in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6e3fe-109">At the base of the stack, frames from the [Windows.UI.Xaml](https://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.aspx) namespace indicate that the XAML rendering engine was running.</span></span>   <span data-ttu-id="6e3fe-110">L'uso del metodo <xref:System.Reflection.PropertyInfo.GetValue%2A?displayProperty=nameWithType> indica una ricerca basata su reflection del valore di una proprietà sul tipo di cui sono stati rimossi i metadati.</span><span class="sxs-lookup"><span data-stu-id="6e3fe-110">The use of the <xref:System.Reflection.PropertyInfo.GetValue%2A?displayProperty=nameWithType> method indicates a reflection-based lookup of a property’s value on the type whose metadata was removed.</span></span>  
  
 <span data-ttu-id="6e3fe-111">Il primo passaggio per la fornitura di una direttiva di metadati consiste nell'aggiunta di metadati `serialize` per il tipo che ne rende accessibili le proprietà:</span><span class="sxs-lookup"><span data-stu-id="6e3fe-111">The first step in providing a metadata directive would be to add `serialize` metadata for the type so that its properties are all accessible:</span></span>  
  
```xml  
<Type Name="App.ViewModels.MainPageVM" Serialize="Required Public" />  
```  
  
## <a name="is-this-an-isolated-case"></a><span data-ttu-id="6e3fe-112">Si tratta di un caso isolato?</span><span class="sxs-lookup"><span data-stu-id="6e3fe-112">Is this an isolated case?</span></span>  
 <span data-ttu-id="6e3fe-113">In questo scenario, se il data binding contiene metadati incompleti per `ViewModel`, potrebbe contenerne anche per altri.</span><span class="sxs-lookup"><span data-stu-id="6e3fe-113">In this scenario, if data binding has incomplete metadata for one `ViewModel`, it may for others, too.</span></span>  <span data-ttu-id="6e3fe-114">Se il codice è strutturato in modo che i modelli di visualizzazione dell'app siano tutti nello spazio dei nomi `App.ViewModels`, è possibile usare una direttiva di runtime più generale:</span><span class="sxs-lookup"><span data-stu-id="6e3fe-114">If the code is structured in a way that the app’s view models are all in the `App.ViewModels` namespace, you could use a more general runtime directive:</span></span>  
  
```xml  
<Namespace Name="App.ViewModels " Serialize="Required Public" />  
```  
  
## <a name="could-the-code-be-rewritten-to-not-use-reflection"></a><span data-ttu-id="6e3fe-115">Il codice può essere riscritto per escludere l'uso della reflection?</span><span class="sxs-lookup"><span data-stu-id="6e3fe-115">Could the code be rewritten to not use reflection?</span></span>  
 <span data-ttu-id="6e3fe-116">Il data binding ha un elevato livello di reflection, pertanto la modifica del codice per impedire la reflection non è consentita.</span><span class="sxs-lookup"><span data-stu-id="6e3fe-116">Because data binding is reflection-intensive, changing the code to avoid reflection isn’t feasible.</span></span>  
  
 <span data-ttu-id="6e3fe-117">Tuttavia, sono disponibili dei metodi per specificare `ViewModel` nella pagina XAML in modo che la catena di strumenti possa associare le associazioni di proprietà al tipo corretto durante la compilazione e mantenere i metadati senza usare una direttiva di runtime.</span><span class="sxs-lookup"><span data-stu-id="6e3fe-117">However, there are ways to specify the `ViewModel` to the XAML page so that the tool chain can associate property bindings with the correct type at compile time and keep the metadata without using a runtime directive.</span></span>  <span data-ttu-id="6e3fe-118">È ad esempio possibile applicare l'attributo [Windows.UI.Xaml.Data.BindableAttribute](https://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.data.bindableattribute.aspx) alle proprietà.</span><span class="sxs-lookup"><span data-stu-id="6e3fe-118">For example, you could apply the [Windows.UI.Xaml.Data.BindableAttribute](https://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.data.bindableattribute.aspx) attribute on properties.</span></span> <span data-ttu-id="6e3fe-119">In questo modo il compilatore XAML genera le informazioni di ricerca necessarie ed evita la richiesta di una direttiva di runtime nel file Default.rd.xml.</span><span class="sxs-lookup"><span data-stu-id="6e3fe-119">This causes the XAML compiler to generate the required lookup information and avoids requiring a runtime directive in the Default.rd.xml file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e3fe-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e3fe-120">See Also</span></span>  
 [<span data-ttu-id="6e3fe-121">Introduzione</span><span class="sxs-lookup"><span data-stu-id="6e3fe-121">Getting Started</span></span>](../../../docs/framework/net-native/getting-started-with-net-native.md)  
 [<span data-ttu-id="6e3fe-122">Esempio: Risoluzione dei problemi di programmazione dinamica</span><span class="sxs-lookup"><span data-stu-id="6e3fe-122">Example: Troubleshooting Dynamic Programming</span></span>](../../../docs/framework/net-native/example-troubleshooting-dynamic-programming.md)
