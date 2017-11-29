---
title: Effetti della modifica dell'aspetto di un form di base
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parent forms [Windows Forms]
- inherited forms [Windows Forms], modifications to base form
- Windows Forms, base form appearance
- base forms
- inheritance [Windows Forms], forms
ms.assetid: 1c3f2b29-a05c-4c6f-aa1a-4e66b94f343a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c1e0eb19946ef2231b5a58df4b8d0b2e40e8e99f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="effects-of-modifying-a-base-form39s-appearance"></a>Effetti della modifica dell'aspetto di un form di base
Durante lo sviluppo di applicazioni, spesso potrebbe essere necessario modificare l'aspetto del form di base da cui ereditano altri form nel progetto (o in altri progetti).  
  
 In fase di progettazione, le modifiche all'aspetto del form di base, relative sia all'impostazione di proprietà o all'aggiunta e sottrazione dei controlli, vengono applicate ai form ereditati quando viene compilato il progetto contenente il form di base. Non è sufficiente salvare le modifiche al form di base. Per compilare un progetto, scegliere **Compila** dal menu **Compila**.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
 Le modifiche apportate al form di base in fase di esecuzione non avranno alcun effetto sui form ereditati in cui è già stata creata un'istanza.  
  
## <a name="see-also"></a>Vedere anche  
 [base](~/docs/csharp/language-reference/keywords/base.md)  
 [Procedura: ereditare Windows Forms](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)  
 [Ereditarietà visiva di Windows Form](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)
