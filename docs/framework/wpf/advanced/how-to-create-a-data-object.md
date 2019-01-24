---
title: 'Procedura: Creare un oggetto dati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataObject class [WPF], creating
- data objects [WPF], creating
- drag-and-drop [WPF], creating data objects
ms.assetid: 022fa142-717d-4fea-a53c-3b52e9d91aff
ms.openlocfilehash: edc301cb896dc8e704a0e17e8e22366d82cc0c17
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54687193"
---
# <a name="how-to-create-a-data-object"></a><span data-ttu-id="39482-102">Procedura: Creare un oggetto dati</span><span class="sxs-lookup"><span data-stu-id="39482-102">How to: Create a Data Object</span></span>
<span data-ttu-id="39482-103">Gli esempi seguenti illustrano vari modi per creare un oggetto dati usando i costruttori forniti dal <xref:System.Windows.DataObject> classe.</span><span class="sxs-lookup"><span data-stu-id="39482-103">The following examples show various ways to create a data object using the constructors provided by the <xref:System.Windows.DataObject> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39482-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="39482-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="39482-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="39482-105">Description</span></span>  
 <span data-ttu-id="39482-106">Esempio di codice seguente crea un nuovo oggetto di dati e viene utilizzato uno dei costruttori di overload (<xref:System.Windows.DataObject.%23ctor%28System.Object%29>) per inizializzare l'oggetto dati con una stringa.</span><span class="sxs-lookup"><span data-stu-id="39482-106">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.Object%29>) to initialize the data object with a string.</span></span>  <span data-ttu-id="39482-107">In questo caso, un formato appropriato dei dati viene determinato automaticamente in base al tipo di dati archiviati e la conversione automatica dei dati archiviati è consentita per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="39482-107">In this case, an appropriate data format is determined automatically according to the stored data's type, and auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="39482-108">Codice</span><span class="sxs-lookup"><span data-stu-id="39482-108">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple)]  
  
### <a name="description"></a><span data-ttu-id="39482-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="39482-109">Description</span></span>  
 <span data-ttu-id="39482-110">Esempio di codice seguente è una versione ridotta di codice riportato sopra.</span><span class="sxs-lookup"><span data-stu-id="39482-110">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="39482-111">Codice</span><span class="sxs-lookup"><span data-stu-id="39482-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple_condensed)]  
  
## <a name="example"></a><span data-ttu-id="39482-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="39482-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="39482-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="39482-113">Description</span></span>  
 <span data-ttu-id="39482-114">Esempio di codice seguente crea un nuovo oggetto di dati e viene utilizzato uno dei costruttori di overload (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>) per inizializzare l'oggetto dati con una stringa e un formato dati specificato.</span><span class="sxs-lookup"><span data-stu-id="39482-114">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="39482-115">In questo caso viene specificato il formato dei dati da una stringa; il <xref:System.Windows.DataFormats> classe fornisce un set di stringhe di tipi predefiniti.</span><span class="sxs-lookup"><span data-stu-id="39482-115">In this case the data format is specified by a string; the <xref:System.Windows.DataFormats> class provides a set of pre-defined type strings.</span></span> <span data-ttu-id="39482-116">Per impostazione predefinita è consentita la conversione automatica dei dati archiviati.</span><span class="sxs-lookup"><span data-stu-id="39482-116">Auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="39482-117">Codice</span><span class="sxs-lookup"><span data-stu-id="39482-117">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
### <a name="description"></a><span data-ttu-id="39482-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="39482-118">Description</span></span>  
 <span data-ttu-id="39482-119">Esempio di codice seguente è una versione ridotta di codice riportato sopra.</span><span class="sxs-lookup"><span data-stu-id="39482-119">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="39482-120">Codice</span><span class="sxs-lookup"><span data-stu-id="39482-120">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring_condensed)]  
  
## <a name="example"></a><span data-ttu-id="39482-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="39482-121">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="39482-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="39482-122">Description</span></span>  
 <span data-ttu-id="39482-123">Esempio di codice seguente crea un nuovo oggetto di dati e viene utilizzato uno dei costruttori di overload (<xref:System.Windows.DataObject.%23ctor%2A>) per inizializzare l'oggetto dati con una stringa e un formato dati specificato.</span><span class="sxs-lookup"><span data-stu-id="39482-123">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%2A>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="39482-124">In questo caso viene specificato il formato dei dati da un <xref:System.Type> parametro.</span><span class="sxs-lookup"><span data-stu-id="39482-124">In this case the data format is specified by a <xref:System.Type> parameter.</span></span>  <span data-ttu-id="39482-125">Per impostazione predefinita è consentita la conversione automatica dei dati archiviati.</span><span class="sxs-lookup"><span data-stu-id="39482-125">Auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="39482-126">Codice</span><span class="sxs-lookup"><span data-stu-id="39482-126">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type)]  
  
### <a name="description"></a><span data-ttu-id="39482-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="39482-127">Description</span></span>  
 <span data-ttu-id="39482-128">Esempio di codice seguente è una versione ridotta di codice riportato sopra.</span><span class="sxs-lookup"><span data-stu-id="39482-128">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="39482-129">Codice</span><span class="sxs-lookup"><span data-stu-id="39482-129">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type_condensed)]  
  
## <a name="example"></a><span data-ttu-id="39482-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="39482-130">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="39482-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="39482-131">Description</span></span>  
 <span data-ttu-id="39482-132">Esempio di codice seguente crea un nuovo oggetto di dati e viene utilizzato uno dei costruttori di overload (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>) per inizializzare l'oggetto dati con una stringa e un formato dati specificato.</span><span class="sxs-lookup"><span data-stu-id="39482-132">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="39482-133">In questo caso viene specificato il formato dei dati da una stringa; il <xref:System.Windows.DataFormats> classe fornisce un set di stringhe di tipi predefiniti.</span><span class="sxs-lookup"><span data-stu-id="39482-133">In this case the data format is specified by a string; the <xref:System.Windows.DataFormats> class provides a set of pre-defined type strings.</span></span> <span data-ttu-id="39482-134">Questo overload del costruttore specifico consente al chiamante di specificare se è consentita la conversione automatica.</span><span class="sxs-lookup"><span data-stu-id="39482-134">This particular constructor overload enables the caller to specify whether auto-converting is allowed.</span></span>  
  
### <a name="code"></a><span data-ttu-id="39482-135">Codice</span><span class="sxs-lookup"><span data-stu-id="39482-135">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert)]  
  
### <a name="description"></a><span data-ttu-id="39482-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="39482-136">Description</span></span>  
 <span data-ttu-id="39482-137">Esempio di codice seguente è una versione ridotta di codice riportato sopra.</span><span class="sxs-lookup"><span data-stu-id="39482-137">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="39482-138">Codice</span><span class="sxs-lookup"><span data-stu-id="39482-138">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert_condensed)]  
  
## <a name="see-also"></a><span data-ttu-id="39482-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39482-139">See also</span></span>
- <xref:System.Windows.IDataObject>
