---
title: 'Procedura: Creare wrapper COM'
description: Creazione di wrapper Component Object Model (COM) utilizzando gli strumenti di Visual Studio o .NET (Tlbimp.exe e Regasm.exe). Entrambi i metodi generano due tipi di wrapper COM.
ms.date: 03/30/2017
helpviewer_keywords:
- COM,wrappers creating
- COM,wrappers Visual Studio
ms.assetid: bdf89bea-1623-45ee-a57b-cf7c90395efa
ms.openlocfilehash: 286526c710287e6efa3e49a7f7c55e3687076e29
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617392"
---
# <a name="how-to-create-com-wrappers"></a>Procedura: Creare wrapper COM

È possibile creare wrapper COM (Component Object Model) usando le funzionalità di Visual Studio 2005 o gli strumenti .NET Framework Tlbimp.exe e Regasm.exe. Entrambi i metodi generano due tipi di wrapper COM:

- Oggetto [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) da una libreria dei tipi per l'esecuzione di un oggetto COM nel codice gestito.

- Oggetto [COM Callable Wrapper](../../standard/native-interop/com-callable-wrapper.md) con le impostazioni del Registro di sistema richieste per l'esecuzione di un oggetto gestito in un'applicazione nativa.

In Visual Studio 2005 è possibile aggiungere il wrapper COM come riferimento al progetto.

## <a name="wrap-com-objects-in-a-managed-application"></a>Eseguire il wrapping di oggetti COM in un'applicazione gestita

### <a name="to-create-a-runtime-callable-wrapper-using-visual-studio"></a>Per creare un Runtime Callable Wrapper con Visual Studio

1. Aprire il progetto per l'applicazione gestita.

2. Scegliere **Mostra tutti i file** dal menu **Progetto**.

3. Scegliere **Aggiungi riferimento** dal menu **Progetto**.

4. Nella finestra di dialogo Aggiungi riferimento fare clic sulla scheda **COM**, selezionare il componente che si vuole usare e fare clic su **OK**.

     In **Esplora soluzioni** si noti che il componente COM viene aggiunto alla cartella Riferimenti nel progetto.

È ora possibile scrivere codice per accedere all'oggetto COM. È possibile iniziare dichiarando l'oggetto, ad esempio con un'istruzione `Imports` per Visual Basic o con un'istruzione `Using` per C#.

> [!NOTE]
> Se si vuole programmare Microsoft Office componenti, installare prima di tutto gli [assembly di interoperabilità primari Microsoft Office ridistribuibili](https://www.microsoft.com/Download/details.aspx?id=3508).
  
### <a name="to-create-a-runtime-callable-wrapper-using-net-framework-tools"></a>Per creare un Runtime Callable Wrapper con gli strumenti di .NET Framework  
  
- Eseguire lo strumento [Tlbimp.exe (utilità di importazione della libreria dei tipi)](../tools/tlbimp-exe-type-library-importer.md).  
  
 Questo strumento crea un assembly che contiene i metadati di runtime per i tipi definiti nella libreria dei tipi originale.  
  
## <a name="wrap-managed-objects-in-a-native-application"></a>Eseguire il wrapping di oggetti gestiti in un'applicazione nativa  
  
### <a name="to-create-a-com-callable-wrapper-using-visual-studio"></a>Per creare un COM Callable Wrapper con Visual Studio  
  
1. Creare un progetto libreria di classi per la classe gestita che si vuole eseguire in codice nativo. La classe deve avere un costruttore senza parametri.  
  
     Verificare che l'assembly nel file AssemblyInfo abbia un numero di versione in quattro parti completo. Questo numero è obbligatorio per la gestione del controllo delle versioni nel Registro di sistema di Windows. Per altre informazioni sui numeri di versione, vedere [Controllo delle versioni degli assembly](../../standard/assembly/versioning.md).  
  
2. Scegliere **Proprietà** dal menu **Progetto**.  
  
3. Fare clic sulla scheda **Compila**.  
  
4. Selezionare la casella di controllo **Registra per interoperabilità COM**.  
  
 Quando si compila il progetto, l'assembly viene automaticamente registrato per l'interoperabilità COM. Se si compila un'applicazione nativa in Visual Studio 2005, è possibile usare l'assembly scegliendo **Aggiungi riferimento** dal menu **Progetto**.  
  
### <a name="to-create-a-com-callable-wrapper-using-net-framework-tools"></a>Per creare un COM Callable Wrapper con gli strumenti di .NET Framework  
  
Eseguire lo strumento [Regasm.exe (strumento di registrazione di assembly)](../tools/regasm-exe-assembly-registration-tool.md).  
  
Questo strumento legge i metadati in un assembly e aggiunge le voci necessarie nel Registro di sistema. Di conseguenza, i client COM possono creare classi di .NET Framework in modo trasparente. È possibile usare l'assembly come se fosse una classe COM nativa.  
  
È possibile eseguire Regasm.exe su un assembly disponibile in qualsiasi directory e quindi eseguire [Gacutil.exe (strumento Global Assembly Cache)](../tools/gacutil-exe-gac-tool.md) per spostarlo nella Global Assembly Cache. Lo spostamento dell'assembly non invalida le voci del Registro di sistema per la posizione, perché la Global Assembly Cache viene sempre esaminata se l'assembly non viene trovato in altre posizioni.  
  
## <a name="see-also"></a>Vedere anche

- [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md)
- [COM Callable Wrapper](../../standard/native-interop/com-callable-wrapper.md)
