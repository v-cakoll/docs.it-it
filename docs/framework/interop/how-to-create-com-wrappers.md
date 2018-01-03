---
title: 'Procedura: creare wrapper COM'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- COM,wrappers creating
- COM,wrappers Visual Studio
ms.assetid: bdf89bea-1623-45ee-a57b-cf7c90395efa
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 646c7fc6a8ebbb68f210637086db0e968e3533c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-com-wrappers"></a>Procedura: creare wrapper COM
È possibile creare wrapper COM (Component Object Model) usando le funzionalità [!INCLUDE[vsprvsext](../../../includes/vsprvsext-md.md)] degli strumenti Tlbimp.exe e Regasm.exe di .NET Framework. Entrambi i metodi generano due tipi di wrapper COM:  
  
-   Oggetto [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) da una libreria dei tipi per l'esecuzione di un oggetto COM nel codice gestito.  
  
-   Oggetto [COM Callable Wrapper](../../../docs/framework/interop/com-callable-wrapper.md) con le impostazioni del Registro di sistema richieste per l'esecuzione di un oggetto gestito in un'applicazione nativa.  
  
 In [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] è possibile aggiungere il wrapper COM come riferimento al progetto.  
  
## <a name="wrapping-com-objects-in-a-managed-application"></a>Wrapping di oggetti COM in un'applicazione gestita  
  
#### <a name="to-create-a-runtime-callable-wrapper-using-visual-studio"></a>Per creare un Runtime Callable Wrapper con Visual Studio  
  
1.  Aprire il progetto per l'applicazione gestita.  
  
2.  Scegliere **Mostra tutti i file** dal menu **Progetto**.  
  
3.  Scegliere **Aggiungi riferimento** dal menu **Progetto**.  
  
4.  Nella finestra di dialogo Aggiungi riferimento fare clic sulla scheda **COM**, selezionare il componente che si vuole usare e fare clic su **OK**.  
  
     In **Esplora soluzioni** si noti che il componente COM viene aggiunto alla cartella Riferimenti nel progetto.  
  
 È ora possibile scrivere codice per accedere all'oggetto COM. È possibile iniziare dichiarando l'oggetto, ad esempio con un'istruzione `Imports` per [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] o un'istruzione `Using` per [!INCLUDE[csprcslong](../../../includes/csprcslong-md.md)].  
  
> [!NOTE]
>  Per programmare componenti di Microsoft Office, installare innanzitutto gli [assembly di interoperabilità primari di Microsoft Office](http://go.microsoft.com/fwlink/?LinkId=50479) dall'Area download Microsoft. Nel passaggio 4 selezionare la versione più recente della libreria di oggetti disponibile per il prodotto Office desiderato, ad esempio la **libreria di oggetti di Microsoft Word 11.0**.  
  
#### <a name="to-create-a-runtime-callable-wrapper-using-net-framework-tools"></a>Per creare un Runtime Callable Wrapper con gli strumenti di .NET Framework  
  
-   Eseguire lo strumento [Tlbimp.exe (utilità di importazione della libreria dei tipi)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md).  
  
 Questo strumento crea un assembly che contiene i metadati di runtime per i tipi definiti nella libreria dei tipi originale.  
  
## <a name="wrapping-managed-objects-in-a-native-application"></a>Wrapping di oggetti gestiti in un'applicazione nativa  
  
#### <a name="to-create-a-com-callable-wrapper-using-visual-studio"></a>Per creare un COM Callable Wrapper con Visual Studio  
  
1.  Creare un progetto libreria di classi per la classe gestita che si vuole eseguire in codice nativo. La classe deve disporre di un costruttore predefinito.  
  
     Verificare che l'assembly nel file AssemblyInfo abbia un numero di versione in quattro parti completo. Questo numero è obbligatorio per la gestione del controllo delle versioni nel Registro di sistema di Windows. Per altre informazioni sui numeri di versione, vedere [Controllo delle versioni degli assembly](../../../docs/framework/app-domains/assembly-versioning.md).  
  
2.  Scegliere **Proprietà** dal menu **Progetto**.  
  
3.  Fare clic sulla scheda **Compila**.  
  
4.  Selezionare la casella di controllo **Registra per interoperabilità COM**.  
  
 Quando si compila il progetto, l'assembly viene automaticamente registrato per l'interoperabilità COM. Se si compila un'applicazione nativa in [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)], è possibile usare l'assembly scegliendo **Aggiungi riferimento** dal menu **Progetto**.  
  
#### <a name="to-create-a-com-callable-wrapper-using-net-framework-tools"></a>Per creare un COM Callable Wrapper con gli strumenti di .NET Framework  
  
-   Eseguire lo strumento [Regasm.exe (strumento di registrazione di assembly)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md).  
  
 Questo strumento legge i metadati in un assembly e aggiunge le voci necessarie nel Registro di sistema. Di conseguenza, i client COM possono creare classi di .NET Framework in modo trasparente. È possibile usare l'assembly come se fosse una classe COM nativa.  
  
 È possibile eseguire Regasm.exe su un assembly disponibile in qualsiasi directory e quindi eseguire [Gacutil.exe (strumento Global Assembly Cache)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) per spostarlo nella Global Assembly Cache. Lo spostamento dell'assembly non invalida le voci del Registro di sistema per la posizione, perché la Global Assembly Cache viene sempre esaminata se l'assembly non viene trovato in altre posizioni.  
  
## <a name="see-also"></a>Vedere anche  
 [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md)  
 [COM Callable Wrapper](../../../docs/framework/interop/com-callable-wrapper.md)
