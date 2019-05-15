---
title: 'Procedura: Spostarsi in un set di dati con il controllo BindingNavigator di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- datasets [Windows Forms], moving through
- BindingNavigator control [Windows Forms], moving through datasets
- examples [Windows Forms], BindingNavigator control
ms.assetid: 146d97be-3d97-400e-accb-860bbf47729d
ms.openlocfilehash: 81b4d574d9fc99f0f002da3e47d81ed17cf8e739
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65588645"
---
# <a name="how-to-move-through-a-dataset-with-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="f8fc7-102">Procedura: Spostarsi in un set di dati con il controllo BindingNavigator di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f8fc7-102">How to: Move Through a DataSet with the Windows Forms BindingNavigator Control</span></span>
<span data-ttu-id="f8fc7-103">Durante la creazione di applicazioni basate sui dati, è spesso necessario visualizzare raccolte di dati agli utenti.</span><span class="sxs-lookup"><span data-stu-id="f8fc7-103">As you build data-driven applications, you will often need to display collections of data to users.</span></span> <span data-ttu-id="f8fc7-104">Il controllo <xref:System.Windows.Forms.BindingNavigator>, unitamente al componente <xref:System.Windows.Forms.BindingSource>, rappresenta una soluzione pratica e versatile per spostarsi all'interno di una raccolta e visualizzare gli elementi in sequenza.</span><span class="sxs-lookup"><span data-stu-id="f8fc7-104">The <xref:System.Windows.Forms.BindingNavigator> control, in conjunction with the <xref:System.Windows.Forms.BindingSource> component, provides a convenient and extensible solution for moving through a collection and displaying items sequentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8fc7-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="f8fc7-105">Example</span></span>  
 <span data-ttu-id="f8fc7-106">L'esempio di codice seguente illustra come usare un controllo <xref:System.Windows.Forms.BindingNavigator> per spostarsi all'interno dei dati.</span><span class="sxs-lookup"><span data-stu-id="f8fc7-106">The following code example demonstrates how to use a <xref:System.Windows.Forms.BindingNavigator> control to move through data.</span></span> <span data-ttu-id="f8fc7-107">Il set è contenuto in una classe <xref:System.Data.DataView>, associata a un controllo <xref:System.Windows.Forms.TextBox> con un componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="f8fc7-107">The set is contained in a <xref:System.Data.DataView>, which is bound to a <xref:System.Windows.Forms.TextBox> control with a <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f8fc7-108">L'archiviazione delle informazioni riservate, ad esempio la password, nella stringa di connessione può avere implicazioni sulla sicurezza dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f8fc7-108">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="f8fc7-109">L'autenticazione di Windows, detta anche sicurezza integrata, consente di controllare l'accesso a un database in modo più sicuro.</span><span class="sxs-lookup"><span data-stu-id="f8fc7-109">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="f8fc7-110">Per altre informazioni, vedere [Protezione delle informazioni di connessione](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="f8fc7-110">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataNavigator#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataNavigator#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f8fc7-111">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="f8fc7-111">Compiling the Code</span></span>  
 <span data-ttu-id="f8fc7-112">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f8fc7-112">This example requires:</span></span>  
  
- <span data-ttu-id="f8fc7-113">Riferimenti agli assembly System, System.Data, System.Drawing, System.Windows.Forms e System.Xml.</span><span class="sxs-lookup"><span data-stu-id="f8fc7-113">References to the System, System.Data, System.Drawing, System.Windows.Forms and System.Xml assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8fc7-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8fc7-114">See also</span></span>

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="f8fc7-115">Controllo BindingNavigator</span><span class="sxs-lookup"><span data-stu-id="f8fc7-115">BindingNavigator Control</span></span>](bindingnavigator-control-windows-forms.md)
- [<span data-ttu-id="f8fc7-116">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="f8fc7-116">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="f8fc7-117">Procedura: Associare un controllo di Windows Form a un tipo</span><span class="sxs-lookup"><span data-stu-id="f8fc7-117">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
