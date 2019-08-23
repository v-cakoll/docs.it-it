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
ms.openlocfilehash: 0b95bab20299b966b9f3c6e6ce089a641670f974
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933418"
---
# <a name="considerations-when-hosting-an-activex-control-on-a-windows-form"></a>Considerazioni sull'inserimento di controlli ActiveX in Windows Form
Anche se Windows Form è stato ottimizzato per ospitare i controlli Windows Form, è tuttavia possibile usare i controlli ActiveX. Quando si pianifica un'applicazione che usa i controlli ActiveX, tenere presenti le considerazioni seguenti:  
  
- **Sicurezza** Common Language Runtime è stato migliorato dal punto di vista della sicurezza dall'accesso di codice. Le applicazioni con Windows Form possono essere eseguite in un ambiente completamente attendibile senza problemi e in un ambiente parzialmente attendibile con accesso alla maggior parte delle funzionalità. I controlli Windows Form possono essere ospitati in un browser senza complicazioni. I controlli ActiveX in Windows Form tuttavia non possono sfruttare i vantaggi offerti da questi miglioramenti della sicurezza. L'esecuzione di un controllo ActiveX richiede l'autorizzazione per il codice non gestito, impostata <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A?displayProperty=nameWithType> con la proprietà. Per ulteriori informazioni sulla sicurezza e sull'autorizzazione per il codice non gestito <xref:System.Security.Permissions.SecurityPermissionAttribute>, vedere.  
  
- **Costo totale di proprietà** I controlli ActiveX aggiunti a un Windows Form vengono interamente distribuiti con tale Windows Form, aumentando considerevolmente le dimensioni dei file creati. Per usare i controlli ActiveX in Windows Form, è anche necessaria un'operazione di scrittura nel Registro di sistema, che è più invasiva per il computer di un utente dei controlli Windows Form, per cui invece non è necessaria.  
  
    > [!NOTE]
    > Per usare un controllo ActiveX, è necessario un wrapper di interoperabilità COM. Per altre informazioni, vedere [Interoperabilità COM in Visual Basic e Visual C#](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
    > [!NOTE]
    > Se il nome di un membro del controllo ActiveX corrisponde a un nome definito nella .NET Framework, l'utilità di importazione del controllo ActiveX aggiungerà un prefisso al nome del membro con **CTL** quando creerà <xref:System.Windows.Forms.AxHost> la classe derivata. Se, ad esempio, il controllo ActiveX dispone di un membro denominato **layout**, viene rinominato **CtlLayout** nella classe derivata da AxHost perché l'evento di **layout** è definito all'interno dell'.NET Framework.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Aggiunta di controlli ActiveX a Windows Forms](how-to-add-activex-controls-to-windows-forms.md)
- [Sicurezza dall'accesso di codice](../../misc/code-access-security.md)
- [Confronto tra controlli e oggetti programmabili in diversi linguaggi e librerie](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))
- [Inserimento di controlli in Windows Form](putting-controls-on-windows-forms.md)
- [Controlli Windows Form](index.md)
