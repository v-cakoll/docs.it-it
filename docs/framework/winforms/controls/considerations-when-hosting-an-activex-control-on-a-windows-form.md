---
title: Considerazioni sull'inserimento di controlli ActiveX in Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- ActiveX controls [Windows Forms], hosting
- Windows Forms, ActiveX controls
- Windows Forms, hosting ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 2509302d-a74e-484f-9890-2acdbfa67a68
ms.openlocfilehash: 52977ea11745056f7e022d545705d989d2e1bbc8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="considerations-when-hosting-an-activex-control-on-a-windows-form"></a>Considerazioni sull'inserimento di controlli ActiveX in Windows Form
Anche se Windows Form è stato ottimizzato per ospitare i controlli Windows Form, è tuttavia possibile usare i controlli ActiveX. Quando si pianifica un'applicazione che usa i controlli ActiveX, tenere presenti le considerazioni seguenti:  
  
-   **Sicurezza** Common Language Runtime è stato migliorato dal punto di vista della sicurezza dall'accesso di codice. Le applicazioni con Windows Form possono essere eseguite in un ambiente completamente attendibile senza problemi e in un ambiente parzialmente attendibile con accesso alla maggior parte delle funzionalità. I controlli Windows Form possono essere ospitati in un browser senza complicazioni. I controlli ActiveX in Windows Form tuttavia non possono sfruttare i vantaggi offerti da questi miglioramenti della sicurezza. Esecuzione di un controllo ActiveX richiede l'autorizzazione di accesso al codice non gestito, che viene impostato con la <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A?displayProperty=nameWithType> proprietà. Per ulteriori informazioni sulla sicurezza e l'autorizzazione per codice non gestito, vedere <xref:System.Security.Permissions.SecurityPermissionAttribute>.  
  
-   **Costo totale di proprietà** I controlli ActiveX aggiunti a un Windows Form vengono interamente distribuiti con tale Windows Form, aumentando considerevolmente le dimensioni dei file creati. Per usare i controlli ActiveX in Windows Form, è anche necessaria un'operazione di scrittura nel Registro di sistema, che è più invasiva per il computer di un utente dei controlli Windows Form, per cui invece non è necessaria.  
  
    > [!NOTE]
    >  Per usare un controllo ActiveX, è necessario un wrapper di interoperabilità COM. Per altre informazioni, vedere [Interoperabilità COM in Visual Basic e Visual C#](~/docs/visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
    > [!NOTE]
    >  Se il nome di un membro del controllo ActiveX corrisponde a un nome definito nel [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], quindi l'utilità di importazione verrà prefisso del nome del membro **Ctl** quando crea la <xref:System.Windows.Forms.AxHost> classe derivata. Se, ad esempio, il controllo ActiveX contiene un membro denominato **Layout**, questo verrà rinominato **CtlLayout** nella classe derivata da AxHost perché l'evento **Layout** è definito in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Aggiungere i controlli ActiveX a Windows Form](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md)  
 [Sicurezza dall'accesso di codice](../../../../docs/framework/misc/code-access-security.md)  
 [Confronto tra controlli e oggetti programmabili in diversi linguaggi e librerie](http://msdn.microsoft.com/library/021f2a1b-8247-4348-a5ad-e1d9ab23004b)  
 [Inserimento di controlli in Windows Form](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)  
 [Controlli Windows Form](../../../../docs/framework/winforms/controls/index.md)
