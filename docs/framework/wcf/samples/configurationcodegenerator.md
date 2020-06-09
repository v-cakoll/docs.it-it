---
title: ConfigurationCodeGenerator
ms.date: 03/30/2017
ms.assetid: 3913aae8-165f-4014-9262-7fe426f90cb2
ms.openlocfilehash: d64be95f71f840e08ede63e1c1f14ee08e52ce97
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84592476"
---
# <a name="configurationcodegenerator"></a><span data-ttu-id="4ede3-102">ConfigurationCodeGenerator</span><span class="sxs-lookup"><span data-stu-id="4ede3-102">ConfigurationCodeGenerator</span></span>
<span data-ttu-id="4ede3-103">ConfigurationCodeGenerator è un strumento che consente di esporre le implementazioni del canale personalizzate nel sistema di configurazione.</span><span class="sxs-lookup"><span data-stu-id="4ede3-103">The ConfigurationCodeGenerator is a tool that you can use to expose your custom channel implementations to the configuration system.</span></span> <span data-ttu-id="4ede3-104">In questo modo gli utenti del canale personalizzato possono configurare il canale utilizzando un file con estensione config nello stesso modo in cui configurerebbero un'associazione fornita dal sistema, ad esempio `NetTcpBinding`, o un'associazione personalizzata utilizzando `TcpTransportBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="4ede3-104">This allows users of your custom channel to configure your channel by using a .config file just as they would configure a system-provided binding such as `NetTcpBinding` or a custom binding using the `TcpTransportBindingElement`.</span></span>  
  
 <span data-ttu-id="4ede3-105">Quando si scrive un canale personalizzato e lo si espone al modello di programmazione utilizzando un elemento `BindingElement` o `Binding` nuovo, è necessario creare un set di classi per rendere `BindingElement` o `Binding` configurabile utilizzando un file config.</span><span class="sxs-lookup"><span data-stu-id="4ede3-105">When you write a custom channel and expose it to the programming model by using a new `BindingElement` or `Binding`, you must create a set of classes to make the `BindingElement` or `Binding` configurable using a .config file.</span></span> <span data-ttu-id="4ede3-106">È possibile utilizzare lo strumento ConfigurationCodeGenerator per generare queste classi e migliorare l'esperienza del cliente.</span><span class="sxs-lookup"><span data-stu-id="4ede3-106">You can use the ConfigurationCodeGenerator tool to generate these classes and enhance your customer's experience.</span></span>  
  
### <a name="to-build-the-tool"></a><span data-ttu-id="4ede3-107">Per compilare lo strumento</span><span class="sxs-lookup"><span data-stu-id="4ede3-107">To build the tool</span></span>  
  
1. <span data-ttu-id="4ede3-108">Per compilare la soluzione, seguire le istruzioni riportate in [compilazione degli esempi di Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4ede3-108">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="4ede3-109">La compilazione della soluzione genera il file ConfigurationCodeGenerator.exe.</span><span class="sxs-lookup"><span data-stu-id="4ede3-109">Building the solution generates one file: ConfigurationCodeGenerator.exe.</span></span> <span data-ttu-id="4ede3-110">Il file SampleRun. cmd include una riga di comando di esempio che illustra come usare questo strumento per generare le classi per l'esempio [Transport: UDP](transport-udp.md) .</span><span class="sxs-lookup"><span data-stu-id="4ede3-110">The file SampleRun.cmd has a sample command line that shows how to use this tool to generate the classes for the [Transport: UDP](transport-udp.md) sample.</span></span>  
  
### <a name="to-run-the-tool"></a><span data-ttu-id="4ede3-111">Per eseguire lo strumento</span><span class="sxs-lookup"><span data-stu-id="4ede3-111">To run the tool</span></span>  
  
1. <span data-ttu-id="4ede3-112">Al prompt dei comandi digitare quanto segue se si dispone di un tipo `BindingElement` personalizzato e un tipo `Binding` personalizzato:</span><span class="sxs-lookup"><span data-stu-id="4ede3-112">At the command prompt type the following if you have both a custom `BindingElement` type and a custom `Binding` type:</span></span>  
  
    ```console  
    ConfigurationCodeGenerator.exe /be:YourCustomBindingElementTypeName /sb:YourCustomStdBindingTypeName /dll:TheAssemblyWhereTheseTypesAreDefined  
    ```  
  
     <span data-ttu-id="4ede3-113">In alternativa, digitare quanto segue se si dispone solo di un tipo `BindingElement` personalizzato:</span><span class="sxs-lookup"><span data-stu-id="4ede3-113">Or type the following if you have only a custom `BindingElement` type:</span></span>  
  
    ```console  
    ConfigurationCodeGenerator.exe /be:YourCustomBindingElementTypeName /dll: TheAssemblyWhereThisTypeIsDefined  
    ```  
  
     <span data-ttu-id="4ede3-114">In alternativa, digitare quanto segue se si dispone solo di un tipo `Binding` personalizzato:</span><span class="sxs-lookup"><span data-stu-id="4ede3-114">Or type the following if you have only a custom `Binding` type:</span></span>  
  
    ```console  
    ConfigurationCodeGenerator.exe /sb:YourCustomStdBindingTypeName /dll:TheAssemblyWhereThisTypeIsDefined  
    ```  
  
     <span data-ttu-id="4ede3-115">Il comando genera tre file con estensione cs per `BindingElement` (se si specifica l'opzione /be:), cinque file cs per l'elemento `Binding` standard (se si specifica l'opzione /sb:) e un file xml.</span><span class="sxs-lookup"><span data-stu-id="4ede3-115">The command generates three .cs files for the `BindingElement` (if you specified the /be: option), five .cs files for the standard `Binding` (if you specified the /sb: option), and a .xml file.</span></span>  
  
    1. <span data-ttu-id="4ede3-116">Se si utilizza l'opzione /be, uno dei file cs implementa `BindingElementExtensionSection` per l'elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="4ede3-116">If you used the /be option, one of the .cs files implements the `BindingElementExtensionSection` for your binding element.</span></span> <span data-ttu-id="4ede3-117">Questo codice espone `BindingElement` al sistema di configurazione, in modo che le altre associazioni personalizzate possono utilizzare l'elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="4ede3-117">This code exposes your `BindingElement` to the configuration system, so that other custom bindings can use your binding element.</span></span> <span data-ttu-id="4ede3-118">Gli altri file dispongono di classi che rappresentano impostazioni predefinite e costanti.</span><span class="sxs-lookup"><span data-stu-id="4ede3-118">The other files have classes that represent defaults and constants.</span></span> <span data-ttu-id="4ede3-119">Nei file sono presenti i commenti `//TODO` per ricordare l'aggiornamento dei valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="4ede3-119">The files have `//TODO` comments to remind you to update the default values.</span></span>  
  
    2. <span data-ttu-id="4ede3-120">Se si specifica il l'opzione /sb, due dei file cs implementano rispettivamente un `StandardBindingElement` e un `StandardBindingCollectionElement` che espongono l'associazione standard al sistema di configurazione.</span><span class="sxs-lookup"><span data-stu-id="4ede3-120">If you specified the /sb option, two of the .cs files implement a `StandardBindingElement` and a `StandardBindingCollectionElement` respectively, which exposes your standard binding to the configuration system.</span></span> <span data-ttu-id="4ede3-121">Gli altri file dispongono di classi che rappresentano impostazioni predefinite e costanti.</span><span class="sxs-lookup"><span data-stu-id="4ede3-121">The other files have classes that represent defaults and constants.</span></span> <span data-ttu-id="4ede3-122">Nei file sono presenti i commenti `//TODO` per ricordare l'aggiornamento dei valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="4ede3-122">The files have `//TODO` comments to remind you to update the default values.</span></span>  
  
         <span data-ttu-id="4ede3-123">Se è stata specificata l'opzione l'/SB: CodeToAddTo \<*YourStdBinding*> . cs contiene codice che è necessario aggiungere manualmente alla classe che implementa l'associazione standard.</span><span class="sxs-lookup"><span data-stu-id="4ede3-123">If you specified the /sb: option the CodeToAddTo\<*YourStdBinding*>.cs has code that you must manually add into the class that implements your standard binding.</span></span>  
  
     <span data-ttu-id="4ede3-124">Il file SampleConfig.xml contiene il codice di configurazione che è necessario aggiungere al file di configurazione che registra i gestori definiti nel passaggio 1 o 2 precedente.</span><span class="sxs-lookup"><span data-stu-id="4ede3-124">The SampleConfig.xml file contains the configuration code that you must add to the configuration file that registers the handlers defined in the previous step 1 or 2.</span></span>  
