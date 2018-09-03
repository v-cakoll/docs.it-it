---
title: 'Procedura: installare un assembly nella Global Assembly Cache'
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- global assembly cache, installing assemblies
- Global Assembly Cache tool
ms.assetid: a7e6f091-d02c-49ba-b736-7295cb0eb743
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8c3bd568cf504125bc99801815d08764417b42cd
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43468998"
---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a>Procedura: installare un assembly nella Global Assembly Cache
Esistono due modi per installare un assembly con nome sicuro nella Global Assembly Cache:  
  
> [!IMPORTANT]
>  Nella GAC possono essere installati solo assembly con nome sicuro. Per informazioni su come creare un assembly con nome sicuro, vedere [Procedura: Firmare un assembly con un nome sicuro](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).  
  
-   Usando [Windows Installer](/windows/desktop/Msi/windows-installer-portal).  
  
     Eseguire questa operazione in Visual Studio 2012 e Visual Studio 2013 creando un progetto InstallShield Limited Edition.  
  
     Si tratta della modalità consigliata e più comune per l'aggiunta di assembly alla Global Assembly Cache. In tal modo si ottiene il conteggio dei riferimenti degli assembly nella Global Assembly Cache e altre utili funzionalità.  
  
-   Usando lo [strumento Global Assembly Cache (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md).  
  
     È possibile usare Gacutil.exe per aggiungere assembly con nome sicuro alla Global Assembly Cache e visualizzare il contenuto di tale cache.  
  
    > [!NOTE]
    >  È necessario usare Gacutil.exe solo in fase di sviluppo e non se ne consiglia l'uso per l'installazione di assembly di produzione nella Global Assembly Cache.  
  
> [!NOTE]
>  Nelle versioni precedenti di .NET Framework, l'estensione della shell di Windows Shfusion.dll consente di installare gli assembly trascinandoli in Esplora file. A partire da [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Shfusion.dll è obsoleto.  
  
### <a name="to-use-the-global-assembly-cache-tool-gacutilexe"></a>Per usare lo strumento Global Assembly Cache (Gacutil.exe).  
  
1.  Al prompt dei comandi digitare il seguente comando:  
  
     **gacutil -i** \<*nome assembly*>  
  
     In questo comando *nome assembly* è il nome dell'assembly da installare nella Global Assembly Cache.  
  
 L'esempio seguente consente di installare un assembly con nome file `hello.dll` nella Global Assembly Cache.  
  
```  
gacutil -i hello.dll  
```  
  
 Per altre informazioni, vedere [Strumento Global Assembly Cache (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md).  
  
### <a name="to-use-an-installshield-limited-edition-project"></a>Per usare un progetto InstallShield Limited Edition  
  
1.  Aggiungere un pacchetto di installazione e distribuzione alla soluzione aprendo il menu di scelta rapida per la soluzione e scegliendo **Aggiungi**, **Nuovo progetto**.  
  
2.  Nella finestra di dialogo **Aggiungi nuovo progetto** nella cartella **Installato** scegliere **Altri tipi di progetto**, **Installazione e distribuzione**, **InstallShield Limited Edition** e assegnare un nome al progetto. (Se richiesto, scaricare, installare e attivare InstallShield.)  
  
3.  Eseguire la configurazione generale del progetto di installazione e di distribuzione usando Project Assistant in **Esplora soluzioni** oppure scegliendo i passaggi secondari dei passaggi numerati in **Esplora soluzioni**. Configurare l'installazione nello stesso modo in cui viene configurata quando non vengono aggiunti assembly nella Global Assembly Cache (GAC).  
  
4.  Per avviare il processo di aggiunta di un assembly nella GAC, scegliere **File** nel passaggio **Specifica dati applicazione** in **Esplora soluzioni**.  
  
5.  Nel riquadro **Cartelle computer di destinazione** aprire il menu di scelta rapida per **Computer di destinazione**, quindi scegliere **Mostra cartella predefinita**, **[GlobalAssemblyCache]**.  
  
6.  Per ogni progetto nella soluzione che contiene un assembly che si desidera installare nella Global Assembly Cache:  
  
    1.  Nel riquadro **Cartelle computer di origine** scegliere il progetto.  
  
    2.  Nel riquadro **Cartelle computer di destinazione** scegliere **[GlobalAssemblyCache]**.  
  
    3.  Nel riquadro **File computer di origine** scegliere **Output primario da** *<nome_progetto>*.  
  
    4.  Trascinare il file nel passaggio c al riquadro di **File computer di destinazione** oppure usare i comandi **Copia** e **Incolla** dal menu di scelta rapida del file.  
  
## <a name="see-also"></a>Vedere anche  
 [Uso di assembly e della Global Assembly Cache](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [Procedura: Rimuovere un assembly dalla Global Assembly Cache](../../../docs/framework/app-domains/how-to-remove-an-assembly-from-the-gac.md)  
 [Gacutil.exe (strumento Global Assembly Cache)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)  
 [Procedura: Firmare un assembly con un nome sicuro](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)  
 [Distribuzione con Windows Installer](https://msdn.microsoft.com/library/121be21b-b916-43e2-8f10-8b080516d2a0)
