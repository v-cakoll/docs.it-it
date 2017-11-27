---
title: 'Procedura: creare un oggetto dati'
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
- DataObject class [WPF], creating
- data objects [WPF], creating
- drag-and-drop [WPF], creating data objects
ms.assetid: 022fa142-717d-4fea-a53c-3b52e9d91aff
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7b002e1c7a9eea2592de58aac3b838b9f6f982ce
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-create-a-data-object"></a><span data-ttu-id="51a2b-102">Procedura: creare un oggetto dati</span><span class="sxs-lookup"><span data-stu-id="51a2b-102">How to: Create a Data Object</span></span>
<span data-ttu-id="51a2b-103">Gli esempi seguenti illustrano diversi modi per creare un oggetto dati usando i costruttori forniti dalla <xref:System.Windows.DataObject> classe.</span><span class="sxs-lookup"><span data-stu-id="51a2b-103">The following examples show various ways to create a data object using the constructors provided by the <xref:System.Windows.DataObject> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51a2b-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="51a2b-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="51a2b-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51a2b-105">Description</span></span>  
 <span data-ttu-id="51a2b-106">Esempio di codice seguente crea un nuovo oggetto dati e viene utilizzato uno dei costruttori di overload (<xref:System.Windows.DataObject.%23ctor%28System.Object%29>) per inizializzare l'oggetto dati con una stringa.</span><span class="sxs-lookup"><span data-stu-id="51a2b-106">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.Object%29>) to initialize the data object with a string.</span></span>  <span data-ttu-id="51a2b-107">In questo caso, un formato appropriato dei dati viene determinato automaticamente in base al tipo di dati archiviati e la conversione automatica dei dati archiviati è consentita per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="51a2b-107">In this case, an appropriate data format is determined automatically according to the stored data's type, and auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="51a2b-108">Codice</span><span class="sxs-lookup"><span data-stu-id="51a2b-108">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple)]  
  
### <a name="description"></a><span data-ttu-id="51a2b-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51a2b-109">Description</span></span>  
 <span data-ttu-id="51a2b-110">Esempio di codice seguente è una versione ridotta di codice sopra riportato.</span><span class="sxs-lookup"><span data-stu-id="51a2b-110">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="51a2b-111">Codice</span><span class="sxs-lookup"><span data-stu-id="51a2b-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple_condensed)]  
  
## <a name="example"></a><span data-ttu-id="51a2b-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="51a2b-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="51a2b-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51a2b-113">Description</span></span>  
 <span data-ttu-id="51a2b-114">Esempio di codice seguente crea un nuovo oggetto dati e viene utilizzato uno dei costruttori di overload (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>) per inizializzare l'oggetto dati con una stringa e un formato dati specificato.</span><span class="sxs-lookup"><span data-stu-id="51a2b-114">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="51a2b-115">In questo caso in cui viene specificato il formato dei dati da una stringa. la <xref:System.Windows.DataFormats> classe fornisce un set di stringhe di tipo predefinite.</span><span class="sxs-lookup"><span data-stu-id="51a2b-115">In this case the data format is specified by a string; the <xref:System.Windows.DataFormats> class provides a set of pre-defined type strings.</span></span> <span data-ttu-id="51a2b-116">La conversione automatica dei dati archiviati è consentita per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="51a2b-116">Auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="51a2b-117">Codice</span><span class="sxs-lookup"><span data-stu-id="51a2b-117">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
### <a name="description"></a><span data-ttu-id="51a2b-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51a2b-118">Description</span></span>  
 <span data-ttu-id="51a2b-119">Esempio di codice seguente è una versione ridotta di codice sopra riportato.</span><span class="sxs-lookup"><span data-stu-id="51a2b-119">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="51a2b-120">Codice</span><span class="sxs-lookup"><span data-stu-id="51a2b-120">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring_condensed)]  
  
## <a name="example"></a><span data-ttu-id="51a2b-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="51a2b-121">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="51a2b-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51a2b-122">Description</span></span>  
 <span data-ttu-id="51a2b-123">Esempio di codice seguente crea un nuovo oggetto dati e viene utilizzato uno dei costruttori di overload (<xref:System.Windows.DataObject.%23ctor%2A>) per inizializzare l'oggetto dati con una stringa e un formato dati specificato.</span><span class="sxs-lookup"><span data-stu-id="51a2b-123">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%2A>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="51a2b-124">In questo caso il formato di dati è specificato da un <xref:System.Type> parametro.</span><span class="sxs-lookup"><span data-stu-id="51a2b-124">In this case the data format is specified by a <xref:System.Type> parameter.</span></span>  <span data-ttu-id="51a2b-125">La conversione automatica dei dati archiviati è consentita per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="51a2b-125">Auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="51a2b-126">Codice</span><span class="sxs-lookup"><span data-stu-id="51a2b-126">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type)]  
  
### <a name="description"></a><span data-ttu-id="51a2b-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51a2b-127">Description</span></span>  
 <span data-ttu-id="51a2b-128">Esempio di codice seguente è una versione ridotta di codice sopra riportato.</span><span class="sxs-lookup"><span data-stu-id="51a2b-128">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="51a2b-129">Codice</span><span class="sxs-lookup"><span data-stu-id="51a2b-129">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type_condensed)]  
  
## <a name="example"></a><span data-ttu-id="51a2b-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="51a2b-130">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="51a2b-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51a2b-131">Description</span></span>  
 <span data-ttu-id="51a2b-132">Esempio di codice seguente crea un nuovo oggetto dati e viene utilizzato uno dei costruttori di overload (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>) per inizializzare l'oggetto dati con una stringa e un formato dati specificato.</span><span class="sxs-lookup"><span data-stu-id="51a2b-132">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="51a2b-133">In questo caso in cui viene specificato il formato dei dati da una stringa. la <xref:System.Windows.DataFormats> classe fornisce un set di stringhe di tipo predefinite.</span><span class="sxs-lookup"><span data-stu-id="51a2b-133">In this case the data format is specified by a string; the <xref:System.Windows.DataFormats> class provides a set of pre-defined type strings.</span></span> <span data-ttu-id="51a2b-134">Questo overload del costruttore particolare consente al chiamante di specificare se è consentita la conversione automatica.</span><span class="sxs-lookup"><span data-stu-id="51a2b-134">This particular constructor overload enables the caller to specify whether auto-converting is allowed.</span></span>  
  
### <a name="code"></a><span data-ttu-id="51a2b-135">Codice</span><span class="sxs-lookup"><span data-stu-id="51a2b-135">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert)]  
  
### <a name="description"></a><span data-ttu-id="51a2b-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51a2b-136">Description</span></span>  
 <span data-ttu-id="51a2b-137">Esempio di codice seguente è una versione ridotta di codice sopra riportato.</span><span class="sxs-lookup"><span data-stu-id="51a2b-137">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="51a2b-138">Codice</span><span class="sxs-lookup"><span data-stu-id="51a2b-138">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert_condensed)]  
  
## <a name="see-also"></a><span data-ttu-id="51a2b-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51a2b-139">See Also</span></span>  
 <xref:System.Windows.IDataObject>
