---
title: Compilazione di applicazioni console in .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework, building console applications
- application development [.NET Framework], console
- console applications
ms.assetid: c21fb997-9f0e-40a5-8741-f73bba376bd8
caps.latest.revision: 16
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: bba3cde0d4e1c15ea764322b8ab0ef1501e53739
ms.contentlocale: it-it
ms.lasthandoff: 08/21/2017

---
# <a name="building-console-applications-in-the-net-framework"></a><span data-ttu-id="acd99-102">Compilazione di applicazioni console in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="acd99-102">Building Console Applications in the .NET Framework</span></span>
<span data-ttu-id="acd99-103">La classe <xref:System.Console?displayProperty=fullName> può essere utilizzata dalle applicazioni in .NET Framework per la lettura e scrittura di caratteri nella console.</span><span class="sxs-lookup"><span data-stu-id="acd99-103">Applications in the .NET Framework can use the <xref:System.Console?displayProperty=fullName> class to read characters from and write characters to the console.</span></span> <span data-ttu-id="acd99-104">I dati provenienti dalla console vengono letti dal flusso di input standard, mentre i dati inviati alla console vengono scritti nel flusso di output standard e i dati di errori inviati alla console vengono scritti nel flusso di output standard degli errori.</span><span class="sxs-lookup"><span data-stu-id="acd99-104">Data from the console is read from the standard input stream, data to the console is written to the standard output stream, and error data to the console is written to the standard error output stream.</span></span> <span data-ttu-id="acd99-105">I flussi vengono associati automaticamente alla console in fase di avvio dell'applicazione e vengono presentati rispettivamente come proprietà <xref:System.Console.In%2A>, <xref:System.Console.Out%2A> ed <xref:System.Console.Error%2A>.</span><span class="sxs-lookup"><span data-stu-id="acd99-105">These streams are automatically associated with the console when the application starts and are presented as the <xref:System.Console.In%2A>, <xref:System.Console.Out%2A>, and <xref:System.Console.Error%2A> properties, respectively.</span></span>  
  
 <span data-ttu-id="acd99-106">Il valore della proprietà <xref:System.Console.In%2A?displayProperty=fullName> è un oggetto <xref:System.IO.TextReader?displayProperty=fullName>, mentre i valori delle proprietà <xref:System.Console.Out%2A?displayProperty=fullName> e <xref:System.Console.Error%2A?displayProperty=fullName> sono oggetti <xref:System.IO.TextWriter?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="acd99-106">The value of the <xref:System.Console.In%2A?displayProperty=fullName> property is a <xref:System.IO.TextReader?displayProperty=fullName> object, whereas the values of the <xref:System.Console.Out%2A?displayProperty=fullName> and <xref:System.Console.Error%2A?displayProperty=fullName> properties are <xref:System.IO.TextWriter?displayProperty=fullName> objects.</span></span> <span data-ttu-id="acd99-107">È possibile associare queste proprietà ai flussi che non rappresentano la console, rendendo possibile l'indirizzamento del flusso a una posizione diversa per l'input e l'output.</span><span class="sxs-lookup"><span data-stu-id="acd99-107">You can associate these properties with streams that do not represent the console, making it possible for you to point the stream to a different location for input or output.</span></span> <span data-ttu-id="acd99-108">È possibile ad esempio reindirizzare l'output in un file impostando la proprietà <xref:System.Console.Out%2A?displayProperty=fullName> su <xref:System.IO.StreamWriter?displayProperty=fullName>, che incapsula un <xref:System.IO.FileStream?displayProperty=fullName> tramite il metodo <xref:System.Console.SetOut%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="acd99-108">For example, you can redirect the output to a file by setting the <xref:System.Console.Out%2A?displayProperty=fullName> property to a <xref:System.IO.StreamWriter?displayProperty=fullName>, which encapsulates a <xref:System.IO.FileStream?displayProperty=fullName> by means of the <xref:System.Console.SetOut%2A?displayProperty=fullName> method.</span></span> <span data-ttu-id="acd99-109">Le proprietà <xref:System.Console.In%2A?displayProperty=fullName> e <xref:System.Console.Out%2A?displayProperty=fullName> non devono fare necessariamente riferimento allo stesso flusso.</span><span class="sxs-lookup"><span data-stu-id="acd99-109">The <xref:System.Console.In%2A?displayProperty=fullName> and <xref:System.Console.Out%2A?displayProperty=fullName> properties do not need to refer to the same stream.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="acd99-110">Per altre informazioni sulla creazione di applicazioni console, inclusi esempi in C#, Visual Basic e C++, vedere la documentazione per la classe <xref:System.Console>.</span><span class="sxs-lookup"><span data-stu-id="acd99-110">For more information about building console applications, including examples in C#, Visual Basic, and C++, see the documentation for the <xref:System.Console> class.</span></span>  
  
 <span data-ttu-id="acd99-111">Se la console non esiste, come in un'applicazione Windows, l'output scritto nel flusso di output standard non sarà visibile, in quanto non è disponibile alcuna console in cui scrivere le informazioni.</span><span class="sxs-lookup"><span data-stu-id="acd99-111">If the console does not exist, as in a Windows-based application, output written to the standard output stream will not be visible, because there is no console to write the information to.</span></span> <span data-ttu-id="acd99-112">La scrittura di informazioni in una console inaccessibile non genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="acd99-112">Writing information to an inaccessible console does not cause an exception to be raised.</span></span>  
  
 <span data-ttu-id="acd99-113">In alternativa, per abilitare la console per la lettura e la scrittura all'interno di un'applicazione basata su Windows sviluppata con Visual Studio, aprire la finestra di dialogo **Proprietà** del progetto, fare clic sulla scheda **Applicazione** e impostare **Tipo applicazione** su **Applicazione console**.</span><span class="sxs-lookup"><span data-stu-id="acd99-113">Alternately, to enable the console for reading and writing within a Windows-based application that is developed using Visual Studio, open the project's **Properties** dialog box, click the **Application** tab, and set the **Application type** to **Console Application**.</span></span>  
  
 <span data-ttu-id="acd99-114">Le applicazioni console non dispongono di un message pump avviato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="acd99-114">Console applications lack a message pump that starts by default.</span></span> <span data-ttu-id="acd99-115">È pertanto possibile che le chiamate ai timer Win32 Microsoft non riescano.</span><span class="sxs-lookup"><span data-stu-id="acd99-115">Therefore, console calls to Microsoft Win32 timers might fail.</span></span>  
  
 <span data-ttu-id="acd99-116">La classe **System.Console** include metodi che consentono di leggere singoli caratteri o intere righe dalla console.</span><span class="sxs-lookup"><span data-stu-id="acd99-116">The **System.Console** class has methods that can read individual characters or entire lines from the console.</span></span> <span data-ttu-id="acd99-117">Altri metodi consentono di convertire dati e formattare stringhe, quindi di scrivere le stringhe formattate nella console.</span><span class="sxs-lookup"><span data-stu-id="acd99-117">Other methods convert data and format strings, and then write the formatted strings to the console.</span></span> <span data-ttu-id="acd99-118">Per altre informazioni sulla formattazione delle stringhe, vedere [Formatting Types](../../docs/standard/base-types/formatting-types.md) (Formattazione dei tipi).</span><span class="sxs-lookup"><span data-stu-id="acd99-118">For more information on formatting strings, see [Formatting Types](../../docs/standard/base-types/formatting-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acd99-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="acd99-119">See Also</span></span>  
 <span data-ttu-id="acd99-120"><xref:System.Console?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="acd99-120"><xref:System.Console?displayProperty=fullName></span></span>   
 [<span data-ttu-id="acd99-121">Formattazione di tipi</span><span class="sxs-lookup"><span data-stu-id="acd99-121">Formatting Types</span></span>](../../docs/standard/base-types/formatting-types.md)

