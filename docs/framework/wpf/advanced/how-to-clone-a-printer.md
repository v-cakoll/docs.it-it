---
title: 'Procedura: Duplicare una stampante'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- print queues [WPF]
- cloning printers [WPF]
- printers [WPF], cloning
- print queues [WPF], cloning
- cloning print queues [WPF]
ms.assetid: dd6997c9-fe04-40f8-88a6-92e3ac0889eb
ms.openlocfilehash: d7a73c6590ca2df00c77a3a7255f2064a8676c42
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54677225"
---
# <a name="how-to-clone-a-printer"></a><span data-ttu-id="9780f-102">Procedura: Duplicare una stampante</span><span class="sxs-lookup"><span data-stu-id="9780f-102">How to: Clone a Printer</span></span>
<span data-ttu-id="9780f-103">La maggior parte delle aziende, a un certo punto acquisti più stampanti dello stesso modello.</span><span class="sxs-lookup"><span data-stu-id="9780f-103">Most businesses will, at some point, buy multiple printers of the same model.</span></span> <span data-ttu-id="9780f-104">In genere, queste vengono installate con le impostazioni di configurazione praticamente identici.</span><span class="sxs-lookup"><span data-stu-id="9780f-104">Typically, these are all installed with virtually identical configuration settings.</span></span> <span data-ttu-id="9780f-105">L'installazione di ogni stampante può richiedere molto tempo e tendente all'errore.</span><span class="sxs-lookup"><span data-stu-id="9780f-105">Installing each printer can be time-consuming and error prone.</span></span> <span data-ttu-id="9780f-106">Il <xref:System.Printing.IndexedProperties?displayProperty=nameWithType> dello spazio dei nomi e il <xref:System.Printing.PrintServer.InstallPrintQueue%2A> classe esposte con Microsoft .NET Framework consente di installare immediatamente un numero qualsiasi di code di stampa aggiuntive che sono stati clonati da una coda di stampa esistente.</span><span class="sxs-lookup"><span data-stu-id="9780f-106">The <xref:System.Printing.IndexedProperties?displayProperty=nameWithType> namespace and the <xref:System.Printing.PrintServer.InstallPrintQueue%2A> class that are exposed with Microsoft .NET Framework makes it possible to instantly install any number of additional print queues that are cloned from an existing print queue.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9780f-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="9780f-107">Example</span></span>  
 <span data-ttu-id="9780f-108">Nell'esempio seguente, una coda di stampa secondo viene clonata da una coda di stampa esistente.</span><span class="sxs-lookup"><span data-stu-id="9780f-108">In the example below, a second print queue is cloned from an existing print queue.</span></span> <span data-ttu-id="9780f-109">Il secondo è diverso dal primo solo nel relativo nome, posizione, porta e lo stato condiviso.</span><span class="sxs-lookup"><span data-stu-id="9780f-109">The second differs from the first only in its name, location, port, and shared status.</span></span> <span data-ttu-id="9780f-110">I passaggi principali per eseguire questa operazione sono come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="9780f-110">The major steps for doing this are as follows.</span></span>  
  
1.  <span data-ttu-id="9780f-111">Creare un <xref:System.Printing.PrintQueue> oggetto per la stampante esistente che sta per essere clonata.</span><span class="sxs-lookup"><span data-stu-id="9780f-111">Create a <xref:System.Printing.PrintQueue> object for the existing printer that is going to be cloned.</span></span>  
  
2.  <span data-ttu-id="9780f-112">Creare un <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> dal <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> del <xref:System.Printing.PrintQueue>.</span><span class="sxs-lookup"><span data-stu-id="9780f-112">Create a <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> from the <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> of the <xref:System.Printing.PrintQueue>.</span></span> <span data-ttu-id="9780f-113">Il <xref:System.Collections.DictionaryEntry.Value%2A> proprietà di ogni voce in questo dizionario è un oggetto di uno dei tipi derivati da <xref:System.Printing.IndexedProperties.PrintProperty>.</span><span class="sxs-lookup"><span data-stu-id="9780f-113">The <xref:System.Collections.DictionaryEntry.Value%2A> property of each entry in this dictionary is an object of one of the types derived from <xref:System.Printing.IndexedProperties.PrintProperty>.</span></span> <span data-ttu-id="9780f-114">Esistono due modi per impostare il valore di una voce in questo dizionario.</span><span class="sxs-lookup"><span data-stu-id="9780f-114">There are two ways to set the value of an entry in this dictionary.</span></span>  
  
    -   <span data-ttu-id="9780f-115">Usare il dizionario **rimuovere** e <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> metodi per rimuovere la voce e quindi aggiungerlo nuovamente con il valore desiderato.</span><span class="sxs-lookup"><span data-stu-id="9780f-115">Use the dictionary's **Remove** and <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> methods to remove the entry and then re-add it with the desired value.</span></span>  
  
    -   <span data-ttu-id="9780f-116">Usare il dizionario <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="9780f-116">Use the dictionary's <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> method.</span></span>  
  
     <span data-ttu-id="9780f-117">L'esempio seguente illustra entrambe le direzioni.</span><span class="sxs-lookup"><span data-stu-id="9780f-117">The example below illustrates both ways.</span></span>  
  
3.  <span data-ttu-id="9780f-118">Creare un <xref:System.Printing.IndexedProperties.PrintBooleanProperty> dell'oggetto e impostare relativi <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> su "IsShared" e la relativa <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> a `true`.</span><span class="sxs-lookup"><span data-stu-id="9780f-118">Create a <xref:System.Printing.IndexedProperties.PrintBooleanProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "IsShared" and its <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> to `true`.</span></span>  
  
4.  <span data-ttu-id="9780f-119">Usare il <xref:System.Printing.IndexedProperties.PrintBooleanProperty> oggetto come valore del <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>della voce "IsShared".</span><span class="sxs-lookup"><span data-stu-id="9780f-119">Use the <xref:System.Printing.IndexedProperties.PrintBooleanProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "IsShared" entry.</span></span>  
  
5.  <span data-ttu-id="9780f-120">Creare un <xref:System.Printing.IndexedProperties.PrintStringProperty> dell'oggetto e impostare relativi <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> a "Nomecondivisione" e la relativa <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> al relativo <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="9780f-120">Create a <xref:System.Printing.IndexedProperties.PrintStringProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "ShareName" and its <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> to an appropriate <xref:System.String>.</span></span>  
  
6.  <span data-ttu-id="9780f-121">Usare la <xref:System.Printing.IndexedProperties.PrintStringProperty> oggetto come valore del <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>della voce "Nomecondivisione".</span><span class="sxs-lookup"><span data-stu-id="9780f-121">Use the <xref:System.Printing.IndexedProperties.PrintStringProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "ShareName" entry.</span></span>  
  
7.  <span data-ttu-id="9780f-122">Creare un'altra <xref:System.Printing.IndexedProperties.PrintStringProperty> dell'oggetto e impostare relativi <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> "Posizione" e la relativa <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> al relativo <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="9780f-122">Create another <xref:System.Printing.IndexedProperties.PrintStringProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "Location" and its <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> to an appropriate <xref:System.String>.</span></span>  
  
8.  <span data-ttu-id="9780f-123">Utilizzare la seconda <xref:System.Printing.IndexedProperties.PrintStringProperty> come valore dell'oggetto di <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>dell'ingresso "Percorso".</span><span class="sxs-lookup"><span data-stu-id="9780f-123">Use the second <xref:System.Printing.IndexedProperties.PrintStringProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "Location" entry.</span></span>  
  
9. <span data-ttu-id="9780f-124">Creare una matrice di <xref:System.String>s.</span><span class="sxs-lookup"><span data-stu-id="9780f-124">Create an array of <xref:System.String>s.</span></span> <span data-ttu-id="9780f-125">Ogni elemento è il nome di una porta nel server.</span><span class="sxs-lookup"><span data-stu-id="9780f-125">Each item is the name of a port on the server.</span></span>  
  
10. <span data-ttu-id="9780f-126">Usare <xref:System.Printing.PrintServer.InstallPrintQueue%2A> per installare la nuova stampante con i nuovi valori.</span><span class="sxs-lookup"><span data-stu-id="9780f-126">Use <xref:System.Printing.PrintServer.InstallPrintQueue%2A> to install the new printer with the new values.</span></span>  
  
 <span data-ttu-id="9780f-127">Seguito è riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="9780f-127">An example is below.</span></span>  
  
 [!code-csharp[ClonePrinter#ClonePrinter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClonePrinter/CSharp/Program.cs#cloneprinter)]
 [!code-vb[ClonePrinter#ClonePrinter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClonePrinter/visualbasic/program.vb#cloneprinter)]  
  
## <a name="see-also"></a><span data-ttu-id="9780f-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9780f-128">See also</span></span>
- <xref:System.Printing.IndexedProperties>
- <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.PrintQueue>
- <xref:System.Collections.DictionaryEntry>
- [<span data-ttu-id="9780f-129">Documenti in WPF</span><span class="sxs-lookup"><span data-stu-id="9780f-129">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
- [<span data-ttu-id="9780f-130">Panoramica della stampa</span><span class="sxs-lookup"><span data-stu-id="9780f-130">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)
