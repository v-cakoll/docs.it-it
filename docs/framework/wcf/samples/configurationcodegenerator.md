---
title: ConfigurationCodeGenerator
ms.date: 03/30/2017
ms.assetid: 3913aae8-165f-4014-9262-7fe426f90cb2
ms.openlocfilehash: 7625060cd0512bb7498a931d7b93a731e52c9f00
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195189"
---
# <a name="configurationcodegenerator"></a><span data-ttu-id="a896b-102">ConfigurationCodeGenerator</span><span class="sxs-lookup"><span data-stu-id="a896b-102">ConfigurationCodeGenerator</span></span>
<span data-ttu-id="a896b-103">ConfigurationCodeGenerator è un strumento che consente di esporre le implementazioni del canale personalizzate nel sistema di configurazione.</span><span class="sxs-lookup"><span data-stu-id="a896b-103">The ConfigurationCodeGenerator is a tool that you can use to expose your custom channel implementations to the configuration system.</span></span> <span data-ttu-id="a896b-104">In questo modo gli utenti del canale personalizzato possono configurare il canale utilizzando un file con estensione config nello stesso modo in cui configurerebbero un'associazione fornita dal sistema, ad esempio `NetTcpBinding`, o un'associazione personalizzata utilizzando `TcpTransportBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="a896b-104">This allows users of your custom channel to configure your channel by using a .config file just as they would configure a system-provided binding such as `NetTcpBinding` or a custom binding using the `TcpTransportBindingElement`.</span></span>  
  
 <span data-ttu-id="a896b-105">Quando si scrive un canale personalizzato e lo si espone al modello di programmazione utilizzando un elemento `BindingElement` o `Binding` nuovo, è necessario creare un set di classi per rendere `BindingElement` o `Binding` configurabile utilizzando un file config.</span><span class="sxs-lookup"><span data-stu-id="a896b-105">When you write a custom channel and expose it to the programming model by using a new `BindingElement` or `Binding`, you must create a set of classes to make the `BindingElement` or `Binding` configurable using a .config file.</span></span> <span data-ttu-id="a896b-106">È possibile utilizzare lo strumento ConfigurationCodeGenerator per generare queste classi e migliorare l'esperienza del cliente.</span><span class="sxs-lookup"><span data-stu-id="a896b-106">You can use the ConfigurationCodeGenerator tool to generate these classes and enhance your customer's experience.</span></span>  
  
### <a name="to-build-the-tool"></a><span data-ttu-id="a896b-107">Per compilare lo strumento</span><span class="sxs-lookup"><span data-stu-id="a896b-107">To build the tool</span></span>  
  
1.  <span data-ttu-id="a896b-108">Per compilare la soluzione, seguire le istruzioni riportate in [Building Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a896b-108">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2.  <span data-ttu-id="a896b-109">La compilazione della soluzione genera il file: ConfigurationCodeGenerator.exe.</span><span class="sxs-lookup"><span data-stu-id="a896b-109">Building the solution generates one file: ConfigurationCodeGenerator.exe.</span></span> <span data-ttu-id="a896b-110">Il file samplerun. cmd ha una riga di comando di esempio che illustra come usare questo strumento per generare le classi per il [trasporto: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) esempio.</span><span class="sxs-lookup"><span data-stu-id="a896b-110">The file SampleRun.cmd has a sample command line that shows how to use this tool to generate the classes for the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span>  
  
### <a name="to-run-the-tool"></a><span data-ttu-id="a896b-111">Per eseguire lo strumento</span><span class="sxs-lookup"><span data-stu-id="a896b-111">To run the tool</span></span>  
  
1.  <span data-ttu-id="a896b-112">Al prompt dei comandi digitare quanto segue se si dispone di un tipo `BindingElement` personalizzato e un tipo `Binding` personalizzato:</span><span class="sxs-lookup"><span data-stu-id="a896b-112">At the command prompt type the following if you have both a custom `BindingElement` type and a custom `Binding` type:</span></span>  
  
    ```  
    ConfigurationCodeGenerator.exe /be:YourCustomBindingElementTypeName /sb:YourCustomStdBindingTypeName /dll:TheAssemblyWhereTheseTypesAreDefined  
    ```  
  
     <span data-ttu-id="a896b-113">In alternativa, digitare quanto segue se si dispone solo di un tipo `BindingElement` personalizzato:</span><span class="sxs-lookup"><span data-stu-id="a896b-113">Or type the following if you have only a custom `BindingElement` type:</span></span>  
  
    ```  
    ConfigurationCodeGenerator.exe /be:YourCustomBindingElementTypeName /dll: TheAssemblyWhereThisTypeIsDefined  
    ```  
  
     <span data-ttu-id="a896b-114">In alternativa, digitare quanto segue se si dispone solo di un tipo `Binding` personalizzato:</span><span class="sxs-lookup"><span data-stu-id="a896b-114">Or type the following if you have only a custom `Binding` type:</span></span>  
  
    ```  
    ConfigurationCodeGenerator.exe /sb:YourCustomStdBindingTypeName /dll:TheAssemblyWhereThisTypeIsDefined  
    ```  
  
     <span data-ttu-id="a896b-115">Il comando genera tre file con estensione cs per `BindingElement` (se si specifica l'opzione /be:), cinque file cs per l'elemento `Binding` standard (se si specifica l'opzione /sb:) e un file xml.</span><span class="sxs-lookup"><span data-stu-id="a896b-115">The command generates three .cs files for the `BindingElement` (if you specified the /be: option), five .cs files for the standard `Binding` (if you specified the /sb: option), and a .xml file.</span></span>  
  
    1.  <span data-ttu-id="a896b-116">Se si utilizza l'opzione /be, uno dei file cs implementa `BindingElementExtensionSection` per l'elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="a896b-116">If you used the /be option, one of the .cs files implements the `BindingElementExtensionSection` for your binding element.</span></span> <span data-ttu-id="a896b-117">Questo codice espone `BindingElement` al sistema di configurazione, in modo che le altre associazioni personalizzate possono utilizzare l'elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="a896b-117">This code exposes your `BindingElement` to the configuration system, so that other custom bindings can use your binding element.</span></span> <span data-ttu-id="a896b-118">Gli altri file dispongono di classi che rappresentano impostazioni predefinite e costanti.</span><span class="sxs-lookup"><span data-stu-id="a896b-118">The other files have classes that represent defaults and constants.</span></span> <span data-ttu-id="a896b-119">Nei file sono presenti i commenti `//TODO` per ricordare l'aggiornamento dei valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="a896b-119">The files have `//TODO` comments to remind you to update the default values.</span></span>  
  
    2.  <span data-ttu-id="a896b-120">Se si specifica il l'opzione /sb, due dei file cs implementano rispettivamente un `StandardBindingElement` e un `StandardBindingCollectionElement` che espongono l'associazione standard al sistema di configurazione.</span><span class="sxs-lookup"><span data-stu-id="a896b-120">If you specified the /sb option, two of the .cs files implement a `StandardBindingElement` and a `StandardBindingCollectionElement` respectively, which exposes your standard binding to the configuration system.</span></span> <span data-ttu-id="a896b-121">Gli altri file dispongono di classi che rappresentano impostazioni predefinite e costanti.</span><span class="sxs-lookup"><span data-stu-id="a896b-121">The other files have classes that represent defaults and constants.</span></span> <span data-ttu-id="a896b-122">Nei file sono presenti i commenti `//TODO` per ricordare l'aggiornamento dei valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="a896b-122">The files have `//TODO` comments to remind you to update the default values.</span></span>  
  
         <span data-ttu-id="a896b-123">Se è stato specificato il /sb: opzione il file CodeToAddTo\<*YourStdBinding*>. cs include il codice che è necessario aggiungere manualmente nella classe che implementa l'associazione standard.</span><span class="sxs-lookup"><span data-stu-id="a896b-123">If you specified the /sb: option the CodeToAddTo\<*YourStdBinding*>.cs has code that you must manually add into the class that implements your standard binding.</span></span>  
  
     <span data-ttu-id="a896b-124">Il file SampleConfig.xml contiene il codice di configurazione che è necessario aggiungere al file di configurazione che registra i gestori definiti nel passaggio 1 o 2 precedente.</span><span class="sxs-lookup"><span data-stu-id="a896b-124">The SampleConfig.xml file contains the configuration code that you must add to the configuration file that registers the handlers defined in the previous step 1 or 2.</span></span>  
