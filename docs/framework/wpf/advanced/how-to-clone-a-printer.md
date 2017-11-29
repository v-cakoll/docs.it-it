---
title: 'Procedura: duplicare una stampante'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 303cb9c1c5b6521839987a56cdc008eac0559cf1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-clone-a-printer"></a><span data-ttu-id="722ed-102">Procedura: duplicare una stampante</span><span class="sxs-lookup"><span data-stu-id="722ed-102">How to: Clone a Printer</span></span>
<span data-ttu-id="722ed-103">A un certo punto, la maggior parte delle aziende acquisterà più stampanti dello stesso modello.</span><span class="sxs-lookup"><span data-stu-id="722ed-103">Most businesses will, at some point, buy multiple printers of the same model.</span></span> <span data-ttu-id="722ed-104">In genere, questi vengono installati con le impostazioni di configurazione praticamente identico.</span><span class="sxs-lookup"><span data-stu-id="722ed-104">Typically, these are all installed with virtually identical configuration settings.</span></span> <span data-ttu-id="722ed-105">Installazione di ogni stampante può richiedere molto tempo e soggetta a errori.</span><span class="sxs-lookup"><span data-stu-id="722ed-105">Installing each printer can be time-consuming and error prone.</span></span> <span data-ttu-id="722ed-106">Il <xref:System.Printing.IndexedProperties?displayProperty=nameWithType> dello spazio dei nomi e <xref:System.Printing.PrintServer.InstallPrintQueue%2A> classe esposta con [!INCLUDE[TLA#tla_avalonwinfx](../../../../includes/tlasharptla-avalonwinfx-md.md)] consente di installare immediatamente qualsiasi numero di code di stampa aggiuntive che vengono clonati da una coda di stampa esistente.</span><span class="sxs-lookup"><span data-stu-id="722ed-106">The <xref:System.Printing.IndexedProperties?displayProperty=nameWithType> namespace and the <xref:System.Printing.PrintServer.InstallPrintQueue%2A> class that are exposed with [!INCLUDE[TLA#tla_avalonwinfx](../../../../includes/tlasharptla-avalonwinfx-md.md)] makes it possible to instantly install any number of additional print queues that are cloned from an existing print queue.</span></span>  
  
## <a name="example"></a><span data-ttu-id="722ed-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="722ed-107">Example</span></span>  
 <span data-ttu-id="722ed-108">Nell'esempio seguente, viene duplicata una seconda coda di stampa da una coda di stampa esistente.</span><span class="sxs-lookup"><span data-stu-id="722ed-108">In the example below, a second print queue is cloned from an existing print queue.</span></span> <span data-ttu-id="722ed-109">Il secondo è diverso dal primo solo nel relativo nome, percorso, porta e lo stato condiviso.</span><span class="sxs-lookup"><span data-stu-id="722ed-109">The second differs from the first only in its name, location, port, and shared status.</span></span> <span data-ttu-id="722ed-110">Come indicato di seguito sono riportati i passaggi principali per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="722ed-110">The major steps for doing this are as follows.</span></span>  
  
1.  <span data-ttu-id="722ed-111">Creare un <xref:System.Printing.PrintQueue> oggetto per la stampante esistente che sta per essere clonata.</span><span class="sxs-lookup"><span data-stu-id="722ed-111">Create a <xref:System.Printing.PrintQueue> object for the existing printer that is going to be cloned.</span></span>  
  
2.  <span data-ttu-id="722ed-112">Creare un <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> dal <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> del <xref:System.Printing.PrintQueue>.</span><span class="sxs-lookup"><span data-stu-id="722ed-112">Create a <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> from the <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> of the <xref:System.Printing.PrintQueue>.</span></span> <span data-ttu-id="722ed-113">Il <xref:System.Collections.DictionaryEntry.Value%2A> proprietà di ciascuna voce del dizionario è un oggetto di uno dei tipi derivati da <xref:System.Printing.IndexedProperties.PrintProperty>.</span><span class="sxs-lookup"><span data-stu-id="722ed-113">The <xref:System.Collections.DictionaryEntry.Value%2A> property of each entry in this dictionary is an object of one of the types derived from <xref:System.Printing.IndexedProperties.PrintProperty>.</span></span> <span data-ttu-id="722ed-114">Esistono due modi per impostare il valore di una voce nel dizionario.</span><span class="sxs-lookup"><span data-stu-id="722ed-114">There are two ways to set the value of an entry in this dictionary.</span></span>  
  
    -   <span data-ttu-id="722ed-115">Utilizzare il dizionario **rimuovere** e <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> metodi per rimuovere la voce e quindi aggiungerlo nuovamente con il valore desiderato.</span><span class="sxs-lookup"><span data-stu-id="722ed-115">Use the dictionary's **Remove** and <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> methods to remove the entry and then re-add it with the desired value.</span></span>  
  
    -   <span data-ttu-id="722ed-116">Utilizzare il dizionario <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="722ed-116">Use the dictionary's <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> method.</span></span>  
  
     <span data-ttu-id="722ed-117">Nell'esempio seguente vengono illustrate entrambe le direzioni.</span><span class="sxs-lookup"><span data-stu-id="722ed-117">The example below illustrates both ways.</span></span>  
  
3.  <span data-ttu-id="722ed-118">Creare un <xref:System.Printing.IndexedProperties.PrintBooleanProperty> e impostare il relativo <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> su "IsShared" e il relativo <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> a `true`.</span><span class="sxs-lookup"><span data-stu-id="722ed-118">Create a <xref:System.Printing.IndexedProperties.PrintBooleanProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "IsShared" and its <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> to `true`.</span></span>  
  
4.  <span data-ttu-id="722ed-119">Utilizzare il <xref:System.Printing.IndexedProperties.PrintBooleanProperty> oggetto come valore del <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>della voce "IsShared".</span><span class="sxs-lookup"><span data-stu-id="722ed-119">Use the <xref:System.Printing.IndexedProperties.PrintBooleanProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "IsShared" entry.</span></span>  
  
5.  <span data-ttu-id="722ed-120">Creare un <xref:System.Printing.IndexedProperties.PrintStringProperty> e impostare il relativo <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> per "Nomecondivisione" e il relativo <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> al relativo <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="722ed-120">Create a <xref:System.Printing.IndexedProperties.PrintStringProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "ShareName" and its <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> to an appropriate <xref:System.String>.</span></span>  
  
6.  <span data-ttu-id="722ed-121">Utilizzare il <xref:System.Printing.IndexedProperties.PrintStringProperty> oggetto come valore del <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>della voce "Nomecondivisione".</span><span class="sxs-lookup"><span data-stu-id="722ed-121">Use the <xref:System.Printing.IndexedProperties.PrintStringProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "ShareName" entry.</span></span>  
  
7.  <span data-ttu-id="722ed-122">Creare un altro <xref:System.Printing.IndexedProperties.PrintStringProperty> e impostare il relativo <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> "Posizione" e il relativo <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> al relativo <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="722ed-122">Create another <xref:System.Printing.IndexedProperties.PrintStringProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "Location" and its <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> to an appropriate <xref:System.String>.</span></span>  
  
8.  <span data-ttu-id="722ed-123">Utilizzare la seconda <xref:System.Printing.IndexedProperties.PrintStringProperty> oggetto come valore del <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>della voce "Location".</span><span class="sxs-lookup"><span data-stu-id="722ed-123">Use the second <xref:System.Printing.IndexedProperties.PrintStringProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "Location" entry.</span></span>  
  
9. <span data-ttu-id="722ed-124">Creare una matrice di <xref:System.String>s.</span><span class="sxs-lookup"><span data-stu-id="722ed-124">Create an array of <xref:System.String>s.</span></span> <span data-ttu-id="722ed-125">Ogni elemento è il nome di una porta nel server.</span><span class="sxs-lookup"><span data-stu-id="722ed-125">Each item is the name of a port on the server.</span></span>  
  
10. <span data-ttu-id="722ed-126">Utilizzare <xref:System.Printing.PrintServer.InstallPrintQueue%2A> per installare la nuova stampante con i nuovi valori.</span><span class="sxs-lookup"><span data-stu-id="722ed-126">Use <xref:System.Printing.PrintServer.InstallPrintQueue%2A> to install the new printer with the new values.</span></span>  
  
 <span data-ttu-id="722ed-127">Un esempio è inferiore.</span><span class="sxs-lookup"><span data-stu-id="722ed-127">An example is below.</span></span>  
  
 [!code-csharp[ClonePrinter#ClonePrinter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClonePrinter/CSharp/Program.cs#cloneprinter)]
 [!code-vb[ClonePrinter#ClonePrinter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClonePrinter/visualbasic/program.vb#cloneprinter)]  
  
## <a name="see-also"></a><span data-ttu-id="722ed-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="722ed-128">See Also</span></span>  
 <xref:System.Printing.IndexedProperties>  
 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Collections.DictionaryEntry>  
 [<span data-ttu-id="722ed-129">Documenti in WPF</span><span class="sxs-lookup"><span data-stu-id="722ed-129">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="722ed-130">Panoramica della stampa</span><span class="sxs-lookup"><span data-stu-id="722ed-130">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)
