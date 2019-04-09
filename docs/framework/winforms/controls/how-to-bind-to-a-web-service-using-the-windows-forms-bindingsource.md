---
title: 'Procedura: Binding a un servizio Web tramite BindingSource di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Web services [Windows Forms], binding controls
- BindingSource component [Windows Forms], binding to a Web service
- examples [Windows Forms], BindingSource component
- controls [Windows Forms], binding to Web service
- BindingSource component [Windows Forms], examples
ms.assetid: ee261207-4573-4cb9-a8cb-5185037e0fba
ms.openlocfilehash: cf5352ff60aabe45473c3c9103e8369597db2e8d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59106756"
---
# <a name="how-to-bind-to-a-web-service-using-the-windows-forms-bindingsource"></a><span data-ttu-id="c31c7-102">Procedura: Binding a un servizio Web tramite BindingSource di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c31c7-102">How to: Bind to a Web Service Using the Windows Forms BindingSource</span></span>
<span data-ttu-id="c31c7-103">Per associare un controllo Windows Form ai risultati ottenuti dalla chiamata a un servizio Web XML, è possibile usare un componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="c31c7-103">If you want to bind a Windows Form control to the results obtained from calling an XML Web service, you can use a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="c31c7-104">Questa procedura è simile al binding di un componente <xref:System.Windows.Forms.BindingSource> a un tipo.</span><span class="sxs-lookup"><span data-stu-id="c31c7-104">This procedure is similar to binding a <xref:System.Windows.Forms.BindingSource> component to a type.</span></span> <span data-ttu-id="c31c7-105">È necessario creare un proxy lato client contenente i metodi e tipi esposti dal servizio Web.</span><span class="sxs-lookup"><span data-stu-id="c31c7-105">You must create a client-side proxy that contains the methods and types exposed by the Web service.</span></span> <span data-ttu-id="c31c7-106">Si genera un proxy lato client direttamente dal servizio Web (asmx) o dal file Web Services Description Language (WSDL).</span><span class="sxs-lookup"><span data-stu-id="c31c7-106">You generate a client-side proxy from the Web service (.asmx) itself, or its Web Services Description Language (WSDL) file.</span></span> <span data-ttu-id="c31c7-107">Inoltre, il proxy lato client deve esporre i campi dei tipi complessi usati dal servizio Web come proprietà pubbliche.</span><span class="sxs-lookup"><span data-stu-id="c31c7-107">Additionally, your client-side proxy must expose the fields of complex types used by the Web service as public properties.</span></span> <span data-ttu-id="c31c7-108">Quindi si associa <xref:System.Windows.Forms.BindingSource> a uno dei tipi esposti nel proxy del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="c31c7-108">You then bind the <xref:System.Windows.Forms.BindingSource> to one of the types exposed in the Web service proxy.</span></span>  
  
### <a name="to-create-and-bind-to-a-client-side-proxy"></a><span data-ttu-id="c31c7-109">Per creare ed eseguire il binding a un proxy lato client</span><span class="sxs-lookup"><span data-stu-id="c31c7-109">To create and bind to a client-side proxy</span></span>  
  
1.  <span data-ttu-id="c31c7-110">Creare un Windows Form nella directory scelta, con uno spazio dei nomi appropriato.</span><span class="sxs-lookup"><span data-stu-id="c31c7-110">Create a Windows Form in the directory of your choice, with an appropriate namespace.</span></span>  
  
2.  <span data-ttu-id="c31c7-111">Aggiungere un componente <xref:System.Windows.Forms.BindingSource> al form.</span><span class="sxs-lookup"><span data-stu-id="c31c7-111">Add a <xref:System.Windows.Forms.BindingSource> component to the form.</span></span>  
  
3.  <span data-ttu-id="c31c7-112">Aprire il prompt dei comandi di [!INCLUDE[winsdklong](../../../../includes/winsdklong-md.md)] e passare alla stessa directory in cui si trova il form.</span><span class="sxs-lookup"><span data-stu-id="c31c7-112">Open the [!INCLUDE[winsdklong](../../../../includes/winsdklong-md.md)] command prompt, and navigate to the same directory that your form is located in.</span></span>  
  
4.  <span data-ttu-id="c31c7-113">Tramite lo strumento WSDL immettere `wsdl` e l'URL del file asmx o WSDL per il servizio Web, seguito dallo spazio dei nomi dell'applicazione e, facoltativamente, dal linguaggio in uso.</span><span class="sxs-lookup"><span data-stu-id="c31c7-113">Using the WSDL tool, enter `wsdl` and the URL for the .asmx or WSDL file for the Web service, followed by the namespace of your application, and optionally the language you are working in.</span></span>  
  
     <span data-ttu-id="c31c7-114">Esempio di codice seguente usa il servizio Web disponibile all'indirizzo `http://webservices.eraserver.net/zipcoderesolver/zipcoderesolver.asmx`.</span><span class="sxs-lookup"><span data-stu-id="c31c7-114">The following code example uses the Web service located at `http://webservices.eraserver.net/zipcoderesolver/zipcoderesolver.asmx`.</span></span> <span data-ttu-id="c31c7-115">Ad esempio, per C# digitare `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService` e per Visual Basic digitare `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService /language:VB`.</span><span class="sxs-lookup"><span data-stu-id="c31c7-115">For example, for C# type `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService`, or for Visual Basic type `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService /language:VB`.</span></span> <span data-ttu-id="c31c7-116">Passando il percorso come argomento allo strumento WSDL, verrà generato un proxy lato client nella stessa directory e nello stesso spazio dei nomi dell'applicazione, nel linguaggio specificato.</span><span class="sxs-lookup"><span data-stu-id="c31c7-116">Passing the path as an argument to the WSDL tool will generate a client-side proxy in the same directory and namespace as your application, in the specified language.</span></span> <span data-ttu-id="c31c7-117">Se si usa Visual Studio, aggiungere il file al progetto.</span><span class="sxs-lookup"><span data-stu-id="c31c7-117">If you are using Visual Studio, add the file to your project.</span></span>  
  
5.  <span data-ttu-id="c31c7-118">Selezionare un tipo nel proxy lato client a cui eseguire il binding.</span><span class="sxs-lookup"><span data-stu-id="c31c7-118">Select a type in the client-side proxy to bind to.</span></span>  
  
     <span data-ttu-id="c31c7-119">In genere si tratta di un tipo restituito da un metodo offerto dal servizio Web.</span><span class="sxs-lookup"><span data-stu-id="c31c7-119">This is typically a type returned by a method offered by the Web service.</span></span> <span data-ttu-id="c31c7-120">I campi del tipo scelto devono essere esposti come proprietà pubbliche ai fini dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="c31c7-120">The fields of the chosen type must be exposed as public properties for binding purposes.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#4)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#4)]  
  
6.  <span data-ttu-id="c31c7-121">Impostare la proprietà <xref:System.Windows.Forms.BindingSource.DataSource%2A> di <xref:System.Windows.Forms.BindingSource> sul tipo desiderato contenuto nel proxy lato client del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="c31c7-121">Set the <xref:System.Windows.Forms.BindingSource.DataSource%2A> property of the <xref:System.Windows.Forms.BindingSource> to the type you want that is contained in the Web service client-side proxy.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#2](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#2)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#2)]  
  
### <a name="to-bind-controls-to-the-bindingsource-that-is-bound-to-a-web-service"></a><span data-ttu-id="c31c7-122">Per associare i controlli all'oggetto BindingSource associato a un servizio Web</span><span class="sxs-lookup"><span data-stu-id="c31c7-122">To bind controls to the BindingSource that is bound to a Web service</span></span>  
  
-   <span data-ttu-id="c31c7-123">Associare i controlli a <xref:System.Windows.Forms.BindingSource>, passando la proprietà pubblica del tipo di servizio Web scelto come parametro.</span><span class="sxs-lookup"><span data-stu-id="c31c7-123">Bind controls to the <xref:System.Windows.Forms.BindingSource>, passing the public property of the Web service type that you want as a parameter.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#3](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#3)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="c31c7-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="c31c7-124">Example</span></span>  
 <span data-ttu-id="c31c7-125">Il seguente esempio di codice mostra come associare un componente <xref:System.Windows.Forms.BindingSource> a un servizio Web e quindi come associare una casella di testo al componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="c31c7-125">The following code example demonstrates how to bind a <xref:System.Windows.Forms.BindingSource> component to a Web service, and then how to bind a text box to the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="c31c7-126">Quando si fa clic sul pulsante, viene chiamato un metodo del servizio Web e i risultati appaiono in `textbox1`.</span><span class="sxs-lookup"><span data-stu-id="c31c7-126">When you click the button, a Web service method is called and the results will appear in `textbox1`.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnectorWebService#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnectorWebService#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorWebService#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c31c7-127">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="c31c7-127">Compiling the Code</span></span>  
 <span data-ttu-id="c31c7-128">Questo è un esempio completo che include un metodo `Main` e una versione abbreviata del codice del proxy lato client.</span><span class="sxs-lookup"><span data-stu-id="c31c7-128">This is a complete example that includes a `Main` method, and a shortened version of client-side proxy code.</span></span>  
  
 <span data-ttu-id="c31c7-129">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c31c7-129">This example requires:</span></span>  
  
-   <span data-ttu-id="c31c7-130">Riferimenti agli assembly System, System.Drawing, System.Web.Services, System.Windows.Forms e System.Xml.</span><span class="sxs-lookup"><span data-stu-id="c31c7-130">References to the System, System.Drawing, System.Web.Services, System.Windows.Forms and System.Xml assemblies.</span></span>  
  
 <span data-ttu-id="c31c7-131">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="c31c7-131">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="c31c7-132">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="c31c7-132">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c31c7-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c31c7-133">See also</span></span>

- [<span data-ttu-id="c31c7-134">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="c31c7-134">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="c31c7-135">Procedura: Associare un controllo di Windows Forms a un tipo</span><span class="sxs-lookup"><span data-stu-id="c31c7-135">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
