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
ms.openlocfilehash: 354c524924794cd240a230e325a4f0eee58cdc50
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705207"
---
# <a name="considerations-when-hosting-an-activex-control-on-a-windows-form"></a>Considerazioni sull'inserimento di controlli ActiveX in Windows Form
Anche se Windows Form è stato ottimizzato per ospitare i controlli Windows Form, è tuttavia possibile usare i controlli ActiveX. Quando si pianifica un'applicazione che usa i controlli ActiveX, tenere presenti le considerazioni seguenti:  
  
-   **Sicurezza** Common Language Runtime è stato migliorato dal punto di vista della sicurezza dall'accesso di codice. Le applicazioni con Windows Form possono essere eseguite in un ambiente completamente attendibile senza problemi e in un ambiente parzialmente attendibile con accesso alla maggior parte delle funzionalità. I controlli Windows Form possono essere ospitati in un browser senza complicazioni. I controlli ActiveX in Windows Form tuttavia non possono sfruttare i vantaggi offerti da questi miglioramenti della sicurezza. Esecuzione di un controllo ActiveX richiede l'autorizzazione per codice non gestito, che viene impostata con il <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A?displayProperty=nameWithType> proprietà. Per altre informazioni sulla sicurezza e autorizzazione al codice non gestito, vedere <xref:System.Security.Permissions.SecurityPermissionAttribute>.  
  
-   **Costo totale di proprietà** I controlli ActiveX aggiunti a un Windows Form vengono interamente distribuiti con tale Windows Form, aumentando considerevolmente le dimensioni dei file creati. Per usare i controlli ActiveX in Windows Form, è anche necessaria un'operazione di scrittura nel Registro di sistema, che è più invasiva per il computer di un utente dei controlli Windows Form, per cui invece non è necessaria.  
  
    > [!NOTE]
    >  Per usare un controllo ActiveX, è necessario un wrapper di interoperabilità COM. Per altre informazioni, vedere [Interoperabilità COM in Visual Basic e Visual C#](~/docs/visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
    > [!NOTE]
    >  Se il nome di un membro del controllo ActiveX corrisponde a un nome definito nel [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], quindi il Control Importer di ActiveX verrà prefisso al nome del membro **Ctl** quando crea il <xref:System.Windows.Forms.AxHost> classe derivata. Se, ad esempio, il controllo ActiveX contiene un membro denominato **Layout**, questo verrà rinominato **CtlLayout** nella classe derivata da AxHost perché l'evento **Layout** è definito in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  
  
## <a name="see-also"></a>Vedere anche
- [Procedura: Aggiungere i controlli ActiveX a Windows Form](how-to-add-activex-controls-to-windows-forms.md)
- [Sicurezza dall'accesso di codice](../../misc/code-access-security.md)
- [Confronto tra controlli e oggetti programmabili in diversi linguaggi e librerie](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))
- [Inserimento di controlli in Windows Form](putting-controls-on-windows-forms.md)
- [Controlli Windows Form](index.md)
