---
title: Sviluppo rapido di applicazioni con My.Resources e My.Settings
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
ms.openlocfilehash: fd1ec25582e919b84235502f5921edfbc6e1dade
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990207"
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a>Sviluppo rapido di applicazioni con My.Resources e My.Settings (Visual Basic)

L' `My.Resources` oggetto fornisce l'accesso alle risorse dell'applicazione e consente di recuperare in modo dinamico le risorse per l'applicazione.  
  
## <a name="retrieving-resources"></a>Recupero di risorse  

 Tramite l'oggetto è possibile recuperare diverse risorse, ad esempio file audio, icone, immagini e stringhe `My.Resources` . Ad esempio, è possibile accedere ai file di risorse specifici delle impostazioni cultura dell'applicazione. Nell'esempio seguente viene impostata l'icona del form sull'icona denominata `Form1Icon` archiviato nel file di risorse dell'applicazione.  
  
 [!code-vb[VbVbcnMy#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#7)]  
  
 L' `My.Resources` oggetto espone solo le risorse globali. Non fornisce l'accesso ai file di risorse associati ai moduli. Accedere alle risorse del modulo dal form.  
  
 Analogamente, l' `My.Settings` oggetto fornisce l'accesso alle impostazioni dell'applicazione e consente di archiviare e recuperare dinamicamente le impostazioni delle proprietà e altre informazioni per l'applicazione. Per altre informazioni, vedere oggetto [My. resources](../../language-reference/objects/my-resources-object.md) e [My. Settings](../../language-reference/objects/my-settings-object.md).  
  
## <a name="see-also"></a>Vedere anche

- [Oggetto My.Resources](../../language-reference/objects/my-resources-object.md)
- [Oggetto My.Settings](../../language-reference/objects/my-settings-object.md)
- [Accessing Application Settings](../programming/app-settings/index.md)
