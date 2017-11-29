---
title: 'Procedura: aggiungere riferimenti alle librerie dei tipi'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- type libraries
- COM interop, importing type library
ms.assetid: f5cfa6ba-cc25-4017-82cd-ba7391859113
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e5bbc99c3c40b0864a7c1c25cb79a3d7c26e3a86
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-references-to-type-libraries"></a>Procedura: aggiungere riferimenti alle librerie dei tipi
Quando si aggiunge un riferimento a una libreria dei tipi, Visual Studio genera un assembly di interoperabilità contenente metadati. Se è disponibile un assembly di interoperabilità primario, prima della generazione di un nuovo assembly di interoperabilità in Visual Studio verrà utilizzato l'assembly esistente.  
  
### <a name="to-add-a-reference-to-a-type-library-in-visual-studio"></a>Per aggiungere un riferimento a una libreria dei tipi in Visual Studio  
  
1.  Installare il file COM DLL o EXE nel computer, a meno che non si esegua l'installazione con un file Setup.exe di Windows.  
  
2.  Scegliere **Progetto**, **Aggiungi riferimento**.  
  
3.  In Gestione riferimenti scegliere **COM**.  
  
4.  Selezionare la libreria dei tipi nell'elenco o cercare il file con estensione tlb.  
  
5.  Scegliere **OK**.  
  
6.  In Esplora soluzioni aprire il menu di scelta rapida per il riferimento appena aggiunto e quindi scegliere **Proprietà**.  
  
7.  Nella finestra **Proprietà** verificare che la proprietà **Incorpora tipi di interoperabilità** sia impostata su **True**. In questo modo Visual Studio incorporerà nei file eseguibili le informazioni sui tipi COM, eliminando l'esigenza di distribuire assembly di interoperabilità primari con l'app.  
  
> [!NOTE]
>  Le opzioni del menu e della finestra di dialogo possono variare a seconda della versione di Visual Studio in uso.  
  
### <a name="to-add-a-reference-to-a-type-library-for-command-line-compilation"></a>Per aggiungere un riferimento a una libreria dei tipi per la compilazione da riga di comando  
  
1.  Generare un assembly di interoperabilità, come descritto in [Procedura: Generare assembly di interoperabilità da librerie dei tipi](../../../docs/framework/interop/how-to-generate-interop-assemblies-from-type-libraries.md).  
  
2.  Usare l'opzione del compilatore [/link (opzioni del compilatore C#)](~/docs/csharp/language-reference/compiler-options/link-compiler-option.md) o [/link (Visual Basic)](~/docs/visual-basic/reference/command-line-compiler/link.md) con il nome dell'assembly di interoperabilità per incorporare informazioni sui tipi COM nei file eseguibili.  
  
## <a name="see-also"></a>Vedere anche  
 [Importazione di una libreria dei tipi come assembly](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)  
 [Esposizione di componenti COM a .NET Framework](../../../docs/framework/interop/exposing-com-components.md)  
 [Procedura dettagliata: Incorporamento delle informazioni sui tipi da assembly di Microsoft Office](http://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3)  
 [Procedura dettagliata: Incorporamento dei tipi da assembly gestiti](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)  
 [/link (opzioni del compilatore C#)](~/docs/csharp/language-reference/compiler-options/link-compiler-option.md)  
 [/link (Visual Basic)](~/docs/visual-basic/reference/command-line-compiler/link.md)
