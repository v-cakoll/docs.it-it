---
title: 'Procedura dettagliata: creazione di oggetti COM con Visual Basic'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- COM interop [Visual Basic], creating COM objects
- COM objects, creating
- COM interop [Visual Basic], walkthroughs
- object creation [Visual Basic], COM objects
- COM objects, walkthroughs
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
caps.latest.revision: 30
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e660d672fc32455cee349dc44ad20c3244c087b4
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a>Procedura dettagliata: creazione di oggetti COM con Visual Basic
Quando si creano nuove applicazioni o componenti, è consigliabile creare gli assembly di .NET Framework. Tuttavia, Visual Basic rende facile la per esporre un componente di .NET Framework a COM. In questo modo è possibile fornire nuovi componenti per la suite di applicazioni precedenti che richiedono i componenti COM. Questa procedura dettagliata viene illustrato come utilizzare Visual Basic per esporre [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] oggetti come oggetti COM, con e senza il modello di classe COM.  
  
 Il modo più semplice per esporre gli oggetti COM è tramite il modello di classe COM. Il modello di classe COM crea una nuova classe e quindi Configura il progetto per generare il livello di classe e l'interoperabilità come un oggetto COM e registrarlo con il sistema operativo.  
  
> [!NOTE]
>  Sebbene sia possibile esporre anche una classe creata in Visual Basic come un oggetto COM per codice non gestito da utilizzare, non è un oggetto COM true e non può essere utilizzato da Visual Basic. Per ulteriori informazioni, vedere [interoperabilità COM nelle applicazioni .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a>Per creare un oggetto COM con modello di classe COM  
  
1.  Aprire un nuovo progetto applicazione Windows dal **File** menu facendo **nuovo progetto**.  
  
2.  Nel **nuovo progetto** nella finestra di dialogo di **tipi di progetto** campo, verificare che Windows sia selezionata. Selezionare **libreria di classi** dal **modelli** elenco e quindi fare clic su **OK**. Viene visualizzato il nuovo progetto.  
  
3.  Selezionare **Aggiungi nuovo elemento** dal **progetto** menu. Verrà visualizzata la finestra di dialogo **Aggiungi nuovo elemento**.  
  
4.  Selezionare **classe COM** dal **modelli** elenco e quindi fare clic su **Aggiungi**. Visual Basic aggiunge una nuova classe e consente di configurare il nuovo progetto per l'interoperabilità COM.  
  
5.  Aggiungere il codice, ad esempio proprietà, metodi ed eventi nella classe COM.  
  
6.  Selezionare **Compila ClassLibrary1** dal **compilare** menu. Visual Basic puoi compilare l'assembly e registrare l'oggetto COM con il sistema operativo.  
  
## <a name="creating-com-objects-without-the-com-class-template"></a>Creazione di oggetti COM senza il modello di classe COM  
 È anche possibile creare una classe COM manualmente, anziché utilizzare il modello di classe COM. Questa procedura è utile quando si utilizza dalla riga di comando oppure quando si desidera maggiore controllo sul modo in cui sono definiti oggetti COM.  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a>Per impostare il progetto per generare un oggetto COM  
  
1.  Aprire un nuovo progetto applicazione Windows dal **File** menu facendo **NewProject**.  
  
2.  Nel **nuovo progetto** nella finestra di dialogo di **tipi di progetto** campo, verificare che Windows sia selezionata. Selezionare **libreria di classi** dal **modelli** elenco e quindi fare clic su **OK**. Viene visualizzato il nuovo progetto.  
  
3.  In **Esplora**mouse sul progetto e quindi fare clic su **proprietà**. Il **progettazione** viene visualizzato.  
  
4.  Fare clic sulla scheda **Compila**.  
  
5.  Selezionare il **Registra per interoperabilità COM** casella di controllo.  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a>Per impostare il codice nella classe per creare un oggetto COM  
  
1.  In **Esplora**, fare doppio clic su **Class1. vb** per visualizzare il codice.  
  
2.  Rinominare la classe come `ComClass1`.  
  
3.  Aggiungere le seguenti costanti per `ComClass1`. Archiviano le costanti di identificatore univoco globale (GUID) che devono disporre gli oggetti COM.  
  
     [!code-vb[VbVbalrInterop#2](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_1.vb)]  
  
4.  Scegliere **Crea GUID** dal menu **Strumenti**. Nella finestra di dialogo **Crea GUID** fare clic su **Formato del Registro di sistema** e quindi fare clic su **Copia**. Fare clic su **Esci**.  
  
5.  Sostituire la stringa vuota per il `ClassId` con il GUID, rimuovendo le iniziali e finali parentesi graffe. Ad esempio, se il GUID fornito da Guidgen è `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` quindi il codice deve essere visualizzata come indicato di seguito.  
  
     [!code-vb[VbVbalrInterop#3](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_2.vb)]  
  
6.  Ripetere i passaggi precedenti per il `InterfaceId` e `EventsId` costanti, come nell'esempio seguente.  
  
     [!code-vb[VbVbalrInterop#4](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_3.vb)]  
  
    > [!NOTE]
    >  Assicurarsi che i GUID siano nuovi e univoci. in caso contrario, il componente COM potrebbe entrare in conflitto con altri componenti COM.  
  
7.  Aggiungere il `ComClass` attributo `ComClass1`, specificando i GUID per l'ID di classe, l'ID di interfaccia e ID degli eventi, come nell'esempio seguente:  
  
     [!code-vb[VbVbalrInterop#5](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_4.vb)]  
  
8.  Classi COM devono avere un costruttore `Public Sub New()` costruttore o la classe non registrare correttamente. Aggiungere un costruttore senza parametri per la classe:  
  
     [!code-vb[VbVbalrInterop#6](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_5.vb)]  
  
9. Aggiungere una proprietà, metodi ed eventi alla classe, che termina con un `End Class` istruzione. Selezionare **Compila soluzione** dal **compilare** menu. Visual Basic puoi compilare l'assembly e registrare l'oggetto COM con il sistema operativo.  
  
    > [!NOTE]
    >  Gli oggetti COM che generare con Visual Basic non possono essere utilizzati da altre applicazioni Visual Basic perché non sono oggetti COM true. Tenta di aggiungere riferimenti a tali oggetti COM genererà un errore. Per informazioni dettagliate, vedere [interoperabilità COM nelle applicazioni .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.ComClassAttribute>  
 [Interoperabilità COM](../../../visual-basic/programming-guide/com-interop/index.md)  
 [Procedura dettagliata: Implementazione dell'ereditarietà con gli oggetti COM](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [Direttiva #Region](../../../visual-basic/language-reference/directives/region-directive.md)  
 [Interoperabilità COM nelle applicazioni .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)  
 [Risoluzione dei problemi relativi all'interoperabilità](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)
