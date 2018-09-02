---
title: 'Procedura: associazione a un servizio Web usando il BindingSource Windows Form'
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
ms.openlocfilehash: fdbf1e1b419e5ad296376ec1f06fd361077895c4
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43406953"
---
# <a name="how-to-bind-to-a-web-service-using-the-windows-forms-bindingsource"></a>Procedura: associazione a un servizio Web usando il BindingSource Windows Form
Per associare un controllo Windows Form ai risultati ottenuti dalla chiamata a un servizio Web XML, è possibile usare un componente <xref:System.Windows.Forms.BindingSource>. Questa procedura è simile al binding di un componente <xref:System.Windows.Forms.BindingSource> a un tipo. È necessario creare un proxy lato client contenente i metodi e tipi esposti dal servizio Web. Si genera un proxy lato client direttamente dal servizio Web (asmx) o dal file Web Services Description Language (WSDL). Inoltre, il proxy lato client deve esporre i campi dei tipi complessi usati dal servizio Web come proprietà pubbliche. Quindi si associa <xref:System.Windows.Forms.BindingSource> a uno dei tipi esposti nel proxy del servizio Web.  
  
### <a name="to-create-and-bind-to-a-client-side-proxy"></a>Per creare ed eseguire il binding a un proxy lato client  
  
1.  Creare un Windows Form nella directory scelta, con uno spazio dei nomi appropriato.  
  
2.  Aggiungere un componente <xref:System.Windows.Forms.BindingSource> al form.  
  
3.  Aprire il prompt dei comandi di [!INCLUDE[winsdklong](../../../../includes/winsdklong-md.md)] e passare alla stessa directory in cui si trova il form.  
  
4.  Tramite lo strumento WSDL immettere `wsdl` e l'URL del file asmx o WSDL per il servizio Web, seguito dallo spazio dei nomi dell'applicazione e, facoltativamente, dal linguaggio in uso.  
  
     Esempio di codice seguente usa il servizio Web disponibile all'indirizzo http://webservices.eraserver.net/zipcoderesolver/zipcoderesolver.asmx. Ad esempio, per C# digitare `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService` e per Visual Basic digitare `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService /language:VB`. Passando il percorso come argomento allo strumento WSDL, verrà generato un proxy lato client nella stessa directory e nello stesso spazio dei nomi dell'applicazione, nel linguaggio specificato. Se si usa Visual Studio, aggiungere il file al progetto.  
  
5.  Selezionare un tipo nel proxy lato client a cui eseguire il binding.  
  
     In genere si tratta di un tipo restituito da un metodo offerto dal servizio Web. I campi del tipo scelto devono essere esposti come proprietà pubbliche ai fini dell'associazione.  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#4)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#4)]  
  
6.  Impostare la proprietà <xref:System.Windows.Forms.BindingSource.DataSource%2A> di <xref:System.Windows.Forms.BindingSource> sul tipo desiderato contenuto nel proxy lato client del servizio Web.  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#2](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#2)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#2)]  
  
### <a name="to-bind-controls-to-the-bindingsource-that-is-bound-to-a-web-service"></a>Per associare i controlli all'oggetto BindingSource associato a un servizio Web  
  
-   Associare i controlli a <xref:System.Windows.Forms.BindingSource>, passando la proprietà pubblica del tipo di servizio Web scelto come parametro.  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#3](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#3)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#3)]  
  
## <a name="example"></a>Esempio  
 Il seguente esempio di codice mostra come associare un componente <xref:System.Windows.Forms.BindingSource> a un servizio Web e quindi come associare una casella di testo al componente <xref:System.Windows.Forms.BindingSource>. Quando si fa clic sul pulsante, viene chiamato un metodo del servizio Web e i risultati appaiono in `textbox1`.  
  
 [!code-cpp[System.Windows.Forms.DataConnectorWebService#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnectorWebService#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorWebService#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Questo è un esempio completo che include un metodo `Main` e una versione abbreviata del codice del proxy lato client.  
  
 L'esempio presenta i requisiti seguenti:  
  
-   Riferimenti agli assembly System, System.Drawing, System.Web.Services, System.Windows.Forms e System.Xml.  
  
 Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.  Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Form completo tramite Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Vedere anche  
 [Componente BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [Procedura: Associare un controllo di Windows Form a un tipo](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)
