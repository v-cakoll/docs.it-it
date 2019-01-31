---
title: "Procedura: Leggere le impostazioni dell'applicazione in Visual Basic"
ms.date: 07/20/2015
helpviewer_keywords:
- reading application settings
- My.Settings object [Visual Basic], reading application settings
- application settings [Visual Basic], reading
ms.assetid: eb3428ef-115e-49a8-a878-e0613183fee0
ms.openlocfilehash: 032e06e674f2298d68f879f3ad474c79e3ff02db
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54659497"
---
# <a name="how-to-read-application-settings-in-visual-basic"></a>Procedura: Leggere le impostazioni dell'applicazione in Visual Basic
È possibile leggere un'impostazione utente accedendo alla proprietà dell'impostazione nell'oggetto `My.Settings`.  
  
 L'oggetto `My.Settings` espone ogni impostazione come proprietà. Il nome della proprietà corrisponde al nome dell'impostazione e il tipo di proprietà al tipo di impostazione. L'**ambito** dell'impostazione indica se la proprietà è di sola lettura. La proprietà di un'impostazione dell'ambito **applicazione** è di sola lettura, mentre la proprietà di un'impostazione dell'ambito **utente** è di lettura e scrittura. Per altre informazioni, vedere [Oggetto My.Settings](../../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato di seguito viene mostrato il valore dell'impostazione `Nickname`.  
  
 [!code-vb[VbVbalrMyResources#14](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-read-application-settings_1.vb)]  
  
 Affinché l'esempio funzioni, l'applicazione deve contenere un'impostazione `Nickname` di tipo `String`. Per altre informazioni, vedere [Gestione delle impostazioni di un'applicazione (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="see-also"></a>Vedere anche
- [Oggetto My.Settings](../../../../visual-basic/language-reference/objects/my-settings-object.md)
- [Procedura: Modificare le impostazioni dell'utente in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [Procedura: Mantenere le impostazioni utente in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [Procedura: Creare griglie di proprietà per impostazioni utente in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [Gestione delle impostazioni di un'applicazione (.NET)](/visualstudio/ide/managing-application-settings-dotnet)
