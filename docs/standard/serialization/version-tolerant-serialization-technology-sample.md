---
title: Esempio di tecnologia di serializzazione indipendente dalla versione
ms.date: 03/30/2017
ms.assetid: 2a183664-bfbf-4ff0-96f6-c836284ea916
ms.openlocfilehash: 317a47d46b839417e01eed9deca2459a96aaa201
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960784"
---
# <a name="version-tolerant-serialization-technology-sample"></a><span data-ttu-id="b37f1-102">Esempio di tecnologia di serializzazione indipendente dalla versione</span><span class="sxs-lookup"><span data-stu-id="b37f1-102">Version Tolerant Serialization Technology Sample</span></span>
[<span data-ttu-id="b37f1-103">Scarica esempio</span><span class="sxs-lookup"><span data-stu-id="b37f1-103">Download Sample</span></span>](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Runtime%20Serialization/VTS.zip.exe)  
  
 <span data-ttu-id="b37f1-104">In questo esempio vengono illustrate le funzionalità relative alla tolleranza dalla versione della serializzazione .NET.</span><span class="sxs-lookup"><span data-stu-id="b37f1-104">This sample demonstrates the version tolerance features of .NET Serialization.</span></span> <span data-ttu-id="b37f1-105">L'esempio compila applicazioni che, nonostante utilizzino versioni diverse di un oggetto <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> per serializzare e deserializzare i dati,</span><span class="sxs-lookup"><span data-stu-id="b37f1-105">The sample builds applications that use different versions of a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> to serialize and deserialize data.</span></span> <span data-ttu-id="b37f1-106">sono in grado di comunicare senza problemi.</span><span class="sxs-lookup"><span data-stu-id="b37f1-106">Despite the presence of different type versions, the applications communicate seamlessly.</span></span> <span data-ttu-id="b37f1-107">Per altre informazioni, vedere [Serializzazione indipendente dalla versione](../../../docs/standard/serialization/version-tolerant-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="b37f1-107">For more information, see [Version Tolerant Serialization](../../../docs/standard/serialization/version-tolerant-serialization.md).</span></span>  
  
### <a name="to-build-the-sample-using-the-command-prompt"></a><span data-ttu-id="b37f1-108">Per compilare l'esempio utilizzando il prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="b37f1-108">To build the sample using the command prompt</span></span>  
  
1. <span data-ttu-id="b37f1-109">Aprire una finestra del prompt dei comandi, quindi spostarsi in una delle sottodirectory specifiche del linguaggio (in V1 Application o V2 Application) relative all'esempio.</span><span class="sxs-lookup"><span data-stu-id="b37f1-109">Open a Command Prompt window and navigate to one of the language-specific subdirectories (under V1 Application or V2 Application) for the sample.</span></span>  
  
2. <span data-ttu-id="b37f1-110">Digitare **msbuild.exe \<ver> application.sln** alla riga di comando (dove \<ver> è v1 o v2).</span><span class="sxs-lookup"><span data-stu-id="b37f1-110">Type **msbuild.exe \<ver> application.sln** at the command line (where \<ver> is either v1 or v2).</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="b37f1-111">Per compilare l'esempio utilizzando Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b37f1-111">To build the sample using Visual Studio</span></span>  
  
1. <span data-ttu-id="b37f1-112">Aprire Esplora file e passare a una delle sottodirectory specifiche del linguaggio per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="b37f1-112">Open File Explorer and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2. <span data-ttu-id="b37f1-113">Spostarsi nella sottodirectory V1 Application della directory selezionata nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="b37f1-113">Navigate to the V1 Application subdirectory of the directory you selected in the previous step.</span></span>  
  
3. <span data-ttu-id="b37f1-114">Fare doppio clic sull'icona relativa a V1 Application.sln per aprire il file in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b37f1-114">Double-click the icon for V1 Application.sln to open the file in Visual Studio.</span></span>  
  
4. <span data-ttu-id="b37f1-115">Nel menu **Compila** scegliere **Compila soluzione**.</span><span class="sxs-lookup"><span data-stu-id="b37f1-115">On the **Build** menu, click **Build Solution**.</span></span>  
  
5. <span data-ttu-id="b37f1-116">Spostarsi nella sottodirectory V2 Application e ripetere i due passaggi precedenti per compilare l'applicazione denominata V2 Application.</span><span class="sxs-lookup"><span data-stu-id="b37f1-116">Navigate to the V2 Application subdirectory and repeat the two previous steps to build the V2 Application.</span></span>  
  
 <span data-ttu-id="b37f1-117">Le applicazioni verranno compilate nelle sottodirectory predefinite \bin o \bin\Debug delle rispettive directory di progetto.</span><span class="sxs-lookup"><span data-stu-id="b37f1-117">The applications will be built in the default \bin or \bin\Debug subdirectories of their respective project directories.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="b37f1-118">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="b37f1-118">To run the sample</span></span>  
  
1. <span data-ttu-id="b37f1-119">Nella finestra del prompt dei comandi spostarsi nella sottodirectory specifica del linguaggio selezionata durante la compilazione delle applicazioni di esempio.</span><span class="sxs-lookup"><span data-stu-id="b37f1-119">In the Command Prompt window, navigate to the language-specific subdirectory that you selected when you built the sample applications.</span></span>  
  
2. <span data-ttu-id="b37f1-120">Digitare **runme.cmd** alla riga di comando per eseguire entrambe le applicazioni contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="b37f1-120">Type **runme.cmd** at the command line to run both applications at once.</span></span>  
  
 <span data-ttu-id="b37f1-121">In alternativa, spostarsi nelle directory contenenti i nuovi eseguibili ed eseguirli in sequenza.</span><span class="sxs-lookup"><span data-stu-id="b37f1-121">Alternatively, navigate to the directories that contain the new executables and run them sequentially.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b37f1-122">L'esempio compila applicazioni console.</span><span class="sxs-lookup"><span data-stu-id="b37f1-122">The sample builds console applications.</span></span> <span data-ttu-id="b37f1-123">Per visualizzare l'output delle applicazioni, è necessario avviarle ed eseguirle in una finestra del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="b37f1-123">You must launch and run them in a Command Prompt window to view their output.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b37f1-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b37f1-124">See also</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>
- <xref:System.IO.FileStream>
