---
title: Raccolte di schemi OLE DB
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: e120ea532b6da455e31ce7345b6c4b2be1ec975f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="625e2-102">Raccolte di schemi OLE DB</span><span class="sxs-lookup"><span data-stu-id="625e2-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="625e2-103">Contenuto della sezione viene descritto il supporto delle raccolte di schemi per i provider OLE DB per Microsoft SQL Server, Oracle e Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="625e2-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="625e2-104">Provider OLE DB per Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="625e2-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="625e2-105">Il Driver OLE DB Microsoft SQL Server supporta le raccolte di schemi specifici seguenti oltre alle raccolte di schemi comuni:</span><span class="sxs-lookup"><span data-stu-id="625e2-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="625e2-106">Tabelle</span><span class="sxs-lookup"><span data-stu-id="625e2-106">Tables</span></span>  
  
-   <span data-ttu-id="625e2-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="625e2-107">Columns</span></span>  
  
-   <span data-ttu-id="625e2-108">Procedure</span><span class="sxs-lookup"><span data-stu-id="625e2-108">Procedures</span></span>  
  
-   <span data-ttu-id="625e2-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="625e2-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="625e2-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="625e2-110">Catalog</span></span>  
  
-   <span data-ttu-id="625e2-111">Indexes</span><span class="sxs-lookup"><span data-stu-id="625e2-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="625e2-112">Tabelle</span><span class="sxs-lookup"><span data-stu-id="625e2-112">Tables</span></span>  
  
|<span data-ttu-id="625e2-113">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="625e2-113">ColumnName</span></span>|<span data-ttu-id="625e2-114">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="625e2-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="625e2-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="625e2-115">TABLE_CATALOG</span></span>|<span data-ttu-id="625e2-116">String</span><span class="sxs-lookup"><span data-stu-id="625e2-116">String</span></span>|  
|<span data-ttu-id="625e2-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="625e2-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="625e2-118">String</span><span class="sxs-lookup"><span data-stu-id="625e2-118">String</span></span>|  
|<span data-ttu-id="625e2-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-119">TABLE_NAME</span></span>|<span data-ttu-id="625e2-120">String</span><span class="sxs-lookup"><span data-stu-id="625e2-120">String</span></span>|  
|<span data-ttu-id="625e2-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="625e2-121">TABLE_TYPE</span></span>|<span data-ttu-id="625e2-122">String</span><span class="sxs-lookup"><span data-stu-id="625e2-122">String</span></span>|  
|<span data-ttu-id="625e2-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="625e2-123">TABLE_GUID</span></span>|<span data-ttu-id="625e2-124">Guid</span><span class="sxs-lookup"><span data-stu-id="625e2-124">Guid</span></span>|  
|<span data-ttu-id="625e2-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="625e2-125">DESCRIPTION</span></span>|<span data-ttu-id="625e2-126">String</span><span class="sxs-lookup"><span data-stu-id="625e2-126">String</span></span>|  
|<span data-ttu-id="625e2-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="625e2-127">TABLE_PROPID</span></span>|<span data-ttu-id="625e2-128">Int64</span><span class="sxs-lookup"><span data-stu-id="625e2-128">Int64</span></span>|  
|<span data-ttu-id="625e2-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="625e2-129">DATE_CREATED</span></span>|<span data-ttu-id="625e2-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="625e2-130">DateTime</span></span>|  
|<span data-ttu-id="625e2-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="625e2-131">DATE_MODIFIED</span></span>|<span data-ttu-id="625e2-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="625e2-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="625e2-133">Colonne</span><span class="sxs-lookup"><span data-stu-id="625e2-133">Columns</span></span>  
  
|<span data-ttu-id="625e2-134">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="625e2-134">ColumnName</span></span>|<span data-ttu-id="625e2-135">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="625e2-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="625e2-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="625e2-136">TABLE_CATALOG</span></span>|<span data-ttu-id="625e2-137">String</span><span class="sxs-lookup"><span data-stu-id="625e2-137">String</span></span>|  
|<span data-ttu-id="625e2-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="625e2-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="625e2-139">String</span><span class="sxs-lookup"><span data-stu-id="625e2-139">String</span></span>|  
|<span data-ttu-id="625e2-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-140">TABLE_NAME</span></span>|<span data-ttu-id="625e2-141">String</span><span class="sxs-lookup"><span data-stu-id="625e2-141">String</span></span>|  
|<span data-ttu-id="625e2-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-142">COLUMN_NAME</span></span>|<span data-ttu-id="625e2-143">String</span><span class="sxs-lookup"><span data-stu-id="625e2-143">String</span></span>|  
|<span data-ttu-id="625e2-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="625e2-144">COLUMN_GUID</span></span>|<span data-ttu-id="625e2-145">Guid</span><span class="sxs-lookup"><span data-stu-id="625e2-145">Guid</span></span>|  
|<span data-ttu-id="625e2-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="625e2-146">COLUMN_PROPID</span></span>|<span data-ttu-id="625e2-147">Int64</span><span class="sxs-lookup"><span data-stu-id="625e2-147">Int64</span></span>|  
|<span data-ttu-id="625e2-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="625e2-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="625e2-149">Int64</span><span class="sxs-lookup"><span data-stu-id="625e2-149">Int64</span></span>|  
|<span data-ttu-id="625e2-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="625e2-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="625e2-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="625e2-151">Boolean</span></span>|  
|<span data-ttu-id="625e2-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="625e2-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="625e2-153">String</span><span class="sxs-lookup"><span data-stu-id="625e2-153">String</span></span>|  
|<span data-ttu-id="625e2-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="625e2-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="625e2-155">Int64</span><span class="sxs-lookup"><span data-stu-id="625e2-155">Int64</span></span>|  
|<span data-ttu-id="625e2-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="625e2-156">IS_NULLABLE</span></span>|<span data-ttu-id="625e2-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="625e2-157">Boolean</span></span>|  
|<span data-ttu-id="625e2-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="625e2-158">DATA_TYPE</span></span>|<span data-ttu-id="625e2-159">Int32</span><span class="sxs-lookup"><span data-stu-id="625e2-159">Int32</span></span>|  
|<span data-ttu-id="625e2-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="625e2-160">TYPE_GUID</span></span>|<span data-ttu-id="625e2-161">Guid</span><span class="sxs-lookup"><span data-stu-id="625e2-161">Guid</span></span>|  
|<span data-ttu-id="625e2-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="625e2-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="625e2-163">Int64</span><span class="sxs-lookup"><span data-stu-id="625e2-163">Int64</span></span>|  
|<span data-ttu-id="625e2-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="625e2-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="625e2-165">Int64</span><span class="sxs-lookup"><span data-stu-id="625e2-165">Int64</span></span>|  
|<span data-ttu-id="625e2-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="625e2-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="625e2-167">Int32</span><span class="sxs-lookup"><span data-stu-id="625e2-167">Int32</span></span>|  
|<span data-ttu-id="625e2-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="625e2-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="625e2-169">Int16</span><span class="sxs-lookup"><span data-stu-id="625e2-169">Int16</span></span>|  
|<span data-ttu-id="625e2-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="625e2-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="625e2-171">Int64</span><span class="sxs-lookup"><span data-stu-id="625e2-171">Int64</span></span>|  
|<span data-ttu-id="625e2-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="625e2-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="625e2-173">String</span><span class="sxs-lookup"><span data-stu-id="625e2-173">String</span></span>|  
|<span data-ttu-id="625e2-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="625e2-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="625e2-175">String</span><span class="sxs-lookup"><span data-stu-id="625e2-175">String</span></span>|  
|<span data-ttu-id="625e2-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="625e2-177">String</span><span class="sxs-lookup"><span data-stu-id="625e2-177">String</span></span>|  
|<span data-ttu-id="625e2-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="625e2-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="625e2-179">String</span><span class="sxs-lookup"><span data-stu-id="625e2-179">String</span></span>|  
|<span data-ttu-id="625e2-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="625e2-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="625e2-181">String</span><span class="sxs-lookup"><span data-stu-id="625e2-181">String</span></span>|  
|<span data-ttu-id="625e2-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-182">COLLATION_NAME</span></span>|<span data-ttu-id="625e2-183">String</span><span class="sxs-lookup"><span data-stu-id="625e2-183">String</span></span>|  
|<span data-ttu-id="625e2-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="625e2-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="625e2-185">String</span><span class="sxs-lookup"><span data-stu-id="625e2-185">String</span></span>|  
|<span data-ttu-id="625e2-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="625e2-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="625e2-187">String</span><span class="sxs-lookup"><span data-stu-id="625e2-187">String</span></span>|  
|<span data-ttu-id="625e2-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-188">DOMAIN_NAME</span></span>|<span data-ttu-id="625e2-189">String</span><span class="sxs-lookup"><span data-stu-id="625e2-189">String</span></span>|  
|<span data-ttu-id="625e2-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="625e2-190">DESCRIPTION</span></span>|<span data-ttu-id="625e2-191">String</span><span class="sxs-lookup"><span data-stu-id="625e2-191">String</span></span>|  
|<span data-ttu-id="625e2-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="625e2-192">COLUMN_LCID</span></span>|<span data-ttu-id="625e2-193">Int32</span><span class="sxs-lookup"><span data-stu-id="625e2-193">Int32</span></span>|  
|<span data-ttu-id="625e2-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="625e2-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="625e2-195">Int32</span><span class="sxs-lookup"><span data-stu-id="625e2-195">Int32</span></span>|  
|<span data-ttu-id="625e2-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="625e2-196">COLUMN_SORTID</span></span>|<span data-ttu-id="625e2-197">Int32</span><span class="sxs-lookup"><span data-stu-id="625e2-197">Int32</span></span>|  
|<span data-ttu-id="625e2-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="625e2-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="625e2-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="625e2-199">Byte[]</span></span>|  
|<span data-ttu-id="625e2-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="625e2-200">IS_COMPUTED</span></span>|<span data-ttu-id="625e2-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="625e2-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="625e2-202">Procedure</span><span class="sxs-lookup"><span data-stu-id="625e2-202">Procedures</span></span>  
  
|<span data-ttu-id="625e2-203">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="625e2-203">ColumnName</span></span>|<span data-ttu-id="625e2-204">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="625e2-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="625e2-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="625e2-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="625e2-206">String</span><span class="sxs-lookup"><span data-stu-id="625e2-206">String</span></span>|  
|<span data-ttu-id="625e2-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="625e2-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="625e2-208">String</span><span class="sxs-lookup"><span data-stu-id="625e2-208">String</span></span>|  
|<span data-ttu-id="625e2-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="625e2-210">String</span><span class="sxs-lookup"><span data-stu-id="625e2-210">String</span></span>|  
|<span data-ttu-id="625e2-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="625e2-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="625e2-212">Int16</span><span class="sxs-lookup"><span data-stu-id="625e2-212">Int16</span></span>|  
|<span data-ttu-id="625e2-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="625e2-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="625e2-214">String</span><span class="sxs-lookup"><span data-stu-id="625e2-214">String</span></span>|  
|<span data-ttu-id="625e2-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="625e2-215">DESCRIPTION</span></span>|<span data-ttu-id="625e2-216">String</span><span class="sxs-lookup"><span data-stu-id="625e2-216">String</span></span>|  
|<span data-ttu-id="625e2-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="625e2-217">DATE_CREATED</span></span>|<span data-ttu-id="625e2-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="625e2-218">DateTime</span></span>|  
|<span data-ttu-id="625e2-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="625e2-219">DATE_MODIFIED</span></span>|<span data-ttu-id="625e2-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="625e2-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="625e2-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="625e2-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="625e2-222">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="625e2-222">ColumnName</span></span>|<span data-ttu-id="625e2-223">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="625e2-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="625e2-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="625e2-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="625e2-225">String</span><span class="sxs-lookup"><span data-stu-id="625e2-225">String</span></span>|  
|<span data-ttu-id="625e2-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="625e2-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="625e2-227">String</span><span class="sxs-lookup"><span data-stu-id="625e2-227">String</span></span>|  
|<span data-ttu-id="625e2-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="625e2-229">String</span><span class="sxs-lookup"><span data-stu-id="625e2-229">String</span></span>|  
|<span data-ttu-id="625e2-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-230">PARAMETER_NAME</span></span>|<span data-ttu-id="625e2-231">String</span><span class="sxs-lookup"><span data-stu-id="625e2-231">String</span></span>|  
|<span data-ttu-id="625e2-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="625e2-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="625e2-233">Int32</span><span class="sxs-lookup"><span data-stu-id="625e2-233">Int32</span></span>|  
|<span data-ttu-id="625e2-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="625e2-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="625e2-235">Int32</span><span class="sxs-lookup"><span data-stu-id="625e2-235">Int32</span></span>|  
|<span data-ttu-id="625e2-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="625e2-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="625e2-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="625e2-237">Boolean</span></span>|  
|<span data-ttu-id="625e2-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="625e2-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="625e2-239">String</span><span class="sxs-lookup"><span data-stu-id="625e2-239">String</span></span>|  
|<span data-ttu-id="625e2-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="625e2-240">IS_NULLABLE</span></span>|<span data-ttu-id="625e2-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="625e2-241">Boolean</span></span>|  
|<span data-ttu-id="625e2-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="625e2-242">DATA_TYPE</span></span>|<span data-ttu-id="625e2-243">Int32</span><span class="sxs-lookup"><span data-stu-id="625e2-243">Int32</span></span>|  
|<span data-ttu-id="625e2-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="625e2-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="625e2-245">Int64</span><span class="sxs-lookup"><span data-stu-id="625e2-245">Int64</span></span>|  
|<span data-ttu-id="625e2-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="625e2-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="625e2-247">Int64</span><span class="sxs-lookup"><span data-stu-id="625e2-247">Int64</span></span>|  
|<span data-ttu-id="625e2-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="625e2-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="625e2-249">Int32</span><span class="sxs-lookup"><span data-stu-id="625e2-249">Int32</span></span>|  
|<span data-ttu-id="625e2-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="625e2-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="625e2-251">Int16</span><span class="sxs-lookup"><span data-stu-id="625e2-251">Int16</span></span>|  
|<span data-ttu-id="625e2-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="625e2-252">DESCRIPTION</span></span>|<span data-ttu-id="625e2-253">String</span><span class="sxs-lookup"><span data-stu-id="625e2-253">String</span></span>|  
|<span data-ttu-id="625e2-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-254">TYPE_NAME</span></span>|<span data-ttu-id="625e2-255">String</span><span class="sxs-lookup"><span data-stu-id="625e2-255">String</span></span>|  
|<span data-ttu-id="625e2-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="625e2-257">String</span><span class="sxs-lookup"><span data-stu-id="625e2-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="625e2-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="625e2-258">Catalog</span></span>  
  
|<span data-ttu-id="625e2-259">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="625e2-259">ColumnName</span></span>|<span data-ttu-id="625e2-260">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="625e2-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="625e2-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-261">CATALOG_NAME</span></span>|<span data-ttu-id="625e2-262">String</span><span class="sxs-lookup"><span data-stu-id="625e2-262">String</span></span>|  
|<span data-ttu-id="625e2-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="625e2-263">DESCRIPTION</span></span>|<span data-ttu-id="625e2-264">String</span><span class="sxs-lookup"><span data-stu-id="625e2-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="625e2-265">Indexes</span><span class="sxs-lookup"><span data-stu-id="625e2-265">Indexes</span></span>  
  
|<span data-ttu-id="625e2-266">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="625e2-266">ColumnName</span></span>|<span data-ttu-id="625e2-267">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="625e2-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="625e2-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="625e2-268">TABLE_CATALOG</span></span>|<span data-ttu-id="625e2-269">String</span><span class="sxs-lookup"><span data-stu-id="625e2-269">String</span></span>|  
|<span data-ttu-id="625e2-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="625e2-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="625e2-271">String</span><span class="sxs-lookup"><span data-stu-id="625e2-271">String</span></span>|  
|<span data-ttu-id="625e2-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-272">TABLE_NAME</span></span>|<span data-ttu-id="625e2-273">String</span><span class="sxs-lookup"><span data-stu-id="625e2-273">String</span></span>|  
|<span data-ttu-id="625e2-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="625e2-274">INDEX_CATALOG</span></span>|<span data-ttu-id="625e2-275">String</span><span class="sxs-lookup"><span data-stu-id="625e2-275">String</span></span>|  
|<span data-ttu-id="625e2-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="625e2-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="625e2-277">String</span><span class="sxs-lookup"><span data-stu-id="625e2-277">String</span></span>|  
|<span data-ttu-id="625e2-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-278">INDEX_NAME</span></span>|<span data-ttu-id="625e2-279">String</span><span class="sxs-lookup"><span data-stu-id="625e2-279">String</span></span>|  
|<span data-ttu-id="625e2-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="625e2-280">PRIMARY_KEY</span></span>|<span data-ttu-id="625e2-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="625e2-281">Boolean</span></span>|  
|<span data-ttu-id="625e2-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="625e2-282">UNIQUE</span></span>|<span data-ttu-id="625e2-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="625e2-283">Boolean</span></span>|  
|<span data-ttu-id="625e2-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="625e2-284">CLUSTERED</span></span>|<span data-ttu-id="625e2-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="625e2-285">Boolean</span></span>|  
|<span data-ttu-id="625e2-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="625e2-286">TYPE</span></span>|<span data-ttu-id="625e2-287">Int32</span><span class="sxs-lookup"><span data-stu-id="625e2-287">Int32</span></span>|  
|<span data-ttu-id="625e2-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="625e2-288">FILL_FACTOR</span></span>|<span data-ttu-id="625e2-289">Int32</span><span class="sxs-lookup"><span data-stu-id="625e2-289">Int32</span></span>|  
|<span data-ttu-id="625e2-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="625e2-290">INITIAL_SIZE</span></span>|<span data-ttu-id="625e2-291">Int32</span><span class="sxs-lookup"><span data-stu-id="625e2-291">Int32</span></span>|  
|<span data-ttu-id="625e2-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="625e2-292">NULLS</span></span>|<span data-ttu-id="625e2-293">Int32</span><span class="sxs-lookup"><span data-stu-id="625e2-293">Int32</span></span>|  
|<span data-ttu-id="625e2-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="625e2-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="625e2-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="625e2-295">Boolean</span></span>|  
|<span data-ttu-id="625e2-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="625e2-296">AUTO_UPDATE</span></span>|<span data-ttu-id="625e2-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="625e2-297">Boolean</span></span>|  
|<span data-ttu-id="625e2-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="625e2-298">NULL_COLLATION</span></span>|<span data-ttu-id="625e2-299">Int32</span><span class="sxs-lookup"><span data-stu-id="625e2-299">Int32</span></span>|  
|<span data-ttu-id="625e2-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="625e2-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="625e2-301">Int64</span><span class="sxs-lookup"><span data-stu-id="625e2-301">Int64</span></span>|  
|<span data-ttu-id="625e2-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-302">COLUMN_NAME</span></span>|<span data-ttu-id="625e2-303">String</span><span class="sxs-lookup"><span data-stu-id="625e2-303">String</span></span>|  
|<span data-ttu-id="625e2-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="625e2-304">COLUMN_GUID</span></span>|<span data-ttu-id="625e2-305">Guid</span><span class="sxs-lookup"><span data-stu-id="625e2-305">Guid</span></span>|  
|<span data-ttu-id="625e2-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="625e2-306">COLUMN_PROPID</span></span>|<span data-ttu-id="625e2-307">Int64</span><span class="sxs-lookup"><span data-stu-id="625e2-307">Int64</span></span>|  
|<span data-ttu-id="625e2-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="625e2-308">COLLATION</span></span>|<span data-ttu-id="625e2-309">Int16</span><span class="sxs-lookup"><span data-stu-id="625e2-309">Int16</span></span>|  
|<span data-ttu-id="625e2-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="625e2-310">CARDINALITY</span></span>|<span data-ttu-id="625e2-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="625e2-311">Decimal</span></span>|  
|<span data-ttu-id="625e2-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="625e2-312">PAGES</span></span>|<span data-ttu-id="625e2-313">Int32</span><span class="sxs-lookup"><span data-stu-id="625e2-313">Int32</span></span>|  
|<span data-ttu-id="625e2-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="625e2-314">FILTER_CONDITION</span></span>|<span data-ttu-id="625e2-315">String</span><span class="sxs-lookup"><span data-stu-id="625e2-315">String</span></span>|  
|<span data-ttu-id="625e2-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="625e2-316">INTEGRATED</span></span>|<span data-ttu-id="625e2-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="625e2-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="625e2-318">Provider OLE DB per Microsoft Oracle</span><span class="sxs-lookup"><span data-stu-id="625e2-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="625e2-319">Oltre alle raccolte di schemi comuni, il driver OLE DB per Microsoft Oracle supporta le seguenti raccolte di schemi specifici:</span><span class="sxs-lookup"><span data-stu-id="625e2-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="625e2-320">Tabelle</span><span class="sxs-lookup"><span data-stu-id="625e2-320">Tables</span></span>  
  
-   <span data-ttu-id="625e2-321">Colonne</span><span class="sxs-lookup"><span data-stu-id="625e2-321">Columns</span></span>  
  
-   <span data-ttu-id="625e2-322">Procedure</span><span class="sxs-lookup"><span data-stu-id="625e2-322">Procedures</span></span>  
  
-   <span data-ttu-id="625e2-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="625e2-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="625e2-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="625e2-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="625e2-325">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="625e2-325">Views</span></span>  
  
-   <span data-ttu-id="625e2-326">Indexes</span><span class="sxs-lookup"><span data-stu-id="625e2-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="625e2-327">Tabelle</span><span class="sxs-lookup"><span data-stu-id="625e2-327">Tables</span></span>  
  
|<span data-ttu-id="625e2-328">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="625e2-328">ColumnName</span></span>|<span data-ttu-id="625e2-329">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="625e2-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="625e2-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="625e2-330">TABLE_CATALOG</span></span>|<span data-ttu-id="625e2-331">String</span><span class="sxs-lookup"><span data-stu-id="625e2-331">String</span></span>|  
|<span data-ttu-id="625e2-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="625e2-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="625e2-333">String</span><span class="sxs-lookup"><span data-stu-id="625e2-333">String</span></span>|  
|<span data-ttu-id="625e2-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-334">TABLE_NAME</span></span>|<span data-ttu-id="625e2-335">String</span><span class="sxs-lookup"><span data-stu-id="625e2-335">String</span></span>|  
|<span data-ttu-id="625e2-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="625e2-336">TABLE_TYPE</span></span>|<span data-ttu-id="625e2-337">String</span><span class="sxs-lookup"><span data-stu-id="625e2-337">String</span></span>|  
|<span data-ttu-id="625e2-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="625e2-338">TABLE_GUID</span></span>|<span data-ttu-id="625e2-339">Guid</span><span class="sxs-lookup"><span data-stu-id="625e2-339">Guid</span></span>|  
|<span data-ttu-id="625e2-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="625e2-340">DESCRIPTION</span></span>|<span data-ttu-id="625e2-341">String</span><span class="sxs-lookup"><span data-stu-id="625e2-341">String</span></span>|  
|<span data-ttu-id="625e2-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="625e2-342">TABLE_PROPID</span></span>|<span data-ttu-id="625e2-343">Int64</span><span class="sxs-lookup"><span data-stu-id="625e2-343">Int64</span></span>|  
|<span data-ttu-id="625e2-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="625e2-344">DATE_CREATED</span></span>|<span data-ttu-id="625e2-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="625e2-345">DateTime</span></span>|  
|<span data-ttu-id="625e2-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="625e2-346">DATE_MODIFIED</span></span>|<span data-ttu-id="625e2-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="625e2-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="625e2-348">Colonne</span><span class="sxs-lookup"><span data-stu-id="625e2-348">Columns</span></span>  
  
|<span data-ttu-id="625e2-349">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="625e2-349">ColumnName</span></span>|<span data-ttu-id="625e2-350">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="625e2-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="625e2-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="625e2-351">TABLE_CATALOG</span></span>|<span data-ttu-id="625e2-352">String</span><span class="sxs-lookup"><span data-stu-id="625e2-352">String</span></span>|  
|<span data-ttu-id="625e2-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="625e2-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="625e2-354">String</span><span class="sxs-lookup"><span data-stu-id="625e2-354">String</span></span>|  
|<span data-ttu-id="625e2-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-355">TABLE_NAME</span></span>|<span data-ttu-id="625e2-356">String</span><span class="sxs-lookup"><span data-stu-id="625e2-356">String</span></span>|  
|<span data-ttu-id="625e2-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-357">COLUMN_NAME</span></span>|<span data-ttu-id="625e2-358">String</span><span class="sxs-lookup"><span data-stu-id="625e2-358">String</span></span>|  
|<span data-ttu-id="625e2-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="625e2-359">COLUMN_GUID</span></span>|<span data-ttu-id="625e2-360">Guid</span><span class="sxs-lookup"><span data-stu-id="625e2-360">Guid</span></span>|  
|<span data-ttu-id="625e2-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="625e2-361">COLUMN_PROPID</span></span>|<span data-ttu-id="625e2-362">Int64</span><span class="sxs-lookup"><span data-stu-id="625e2-362">Int64</span></span>|  
|<span data-ttu-id="625e2-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="625e2-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="625e2-364">Int64</span><span class="sxs-lookup"><span data-stu-id="625e2-364">Int64</span></span>|  
|<span data-ttu-id="625e2-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="625e2-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="625e2-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="625e2-366">Boolean</span></span>|  
|<span data-ttu-id="625e2-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="625e2-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="625e2-368">String</span><span class="sxs-lookup"><span data-stu-id="625e2-368">String</span></span>|  
|<span data-ttu-id="625e2-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="625e2-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="625e2-370">Int64</span><span class="sxs-lookup"><span data-stu-id="625e2-370">Int64</span></span>|  
|<span data-ttu-id="625e2-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="625e2-371">IS_NULLABLE</span></span>|<span data-ttu-id="625e2-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="625e2-372">Boolean</span></span>|  
|<span data-ttu-id="625e2-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="625e2-373">DATA_TYPE</span></span>|<span data-ttu-id="625e2-374">Int32</span><span class="sxs-lookup"><span data-stu-id="625e2-374">Int32</span></span>|  
|<span data-ttu-id="625e2-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="625e2-375">TYPE_GUID</span></span>|<span data-ttu-id="625e2-376">Guid</span><span class="sxs-lookup"><span data-stu-id="625e2-376">Guid</span></span>|  
|<span data-ttu-id="625e2-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="625e2-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="625e2-378">Int64</span><span class="sxs-lookup"><span data-stu-id="625e2-378">Int64</span></span>|  
|<span data-ttu-id="625e2-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="625e2-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="625e2-380">Int64</span><span class="sxs-lookup"><span data-stu-id="625e2-380">Int64</span></span>|  
|<span data-ttu-id="625e2-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="625e2-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="625e2-382">Int32</span><span class="sxs-lookup"><span data-stu-id="625e2-382">Int32</span></span>|  
|<span data-ttu-id="625e2-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="625e2-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="625e2-384">Int16</span><span class="sxs-lookup"><span data-stu-id="625e2-384">Int16</span></span>|  
|<span data-ttu-id="625e2-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="625e2-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="625e2-386">Int64</span><span class="sxs-lookup"><span data-stu-id="625e2-386">Int64</span></span>|  
|<span data-ttu-id="625e2-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="625e2-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="625e2-388">String</span><span class="sxs-lookup"><span data-stu-id="625e2-388">String</span></span>|  
|<span data-ttu-id="625e2-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="625e2-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="625e2-390">String</span><span class="sxs-lookup"><span data-stu-id="625e2-390">String</span></span>|  
|<span data-ttu-id="625e2-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="625e2-392">String</span><span class="sxs-lookup"><span data-stu-id="625e2-392">String</span></span>|  
|<span data-ttu-id="625e2-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="625e2-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="625e2-394">String</span><span class="sxs-lookup"><span data-stu-id="625e2-394">String</span></span>|  
|<span data-ttu-id="625e2-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="625e2-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="625e2-396">String</span><span class="sxs-lookup"><span data-stu-id="625e2-396">String</span></span>|  
|<span data-ttu-id="625e2-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-397">COLLATION_NAME</span></span>|<span data-ttu-id="625e2-398">String</span><span class="sxs-lookup"><span data-stu-id="625e2-398">String</span></span>|  
|<span data-ttu-id="625e2-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="625e2-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="625e2-400">String</span><span class="sxs-lookup"><span data-stu-id="625e2-400">String</span></span>|  
|<span data-ttu-id="625e2-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="625e2-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="625e2-402">String</span><span class="sxs-lookup"><span data-stu-id="625e2-402">String</span></span>|  
|<span data-ttu-id="625e2-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-403">DOMAIN_NAME</span></span>|<span data-ttu-id="625e2-404">String</span><span class="sxs-lookup"><span data-stu-id="625e2-404">String</span></span>|  
|<span data-ttu-id="625e2-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="625e2-405">DESCRIPTION</span></span>|<span data-ttu-id="625e2-406">String</span><span class="sxs-lookup"><span data-stu-id="625e2-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="625e2-407">Procedure</span><span class="sxs-lookup"><span data-stu-id="625e2-407">Procedures</span></span>  
  
|<span data-ttu-id="625e2-408">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="625e2-408">ColumnName</span></span>|<span data-ttu-id="625e2-409">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="625e2-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="625e2-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="625e2-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="625e2-411">String</span><span class="sxs-lookup"><span data-stu-id="625e2-411">String</span></span>|  
|<span data-ttu-id="625e2-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="625e2-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="625e2-413">String</span><span class="sxs-lookup"><span data-stu-id="625e2-413">String</span></span>|  
|<span data-ttu-id="625e2-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="625e2-415">String</span><span class="sxs-lookup"><span data-stu-id="625e2-415">String</span></span>|  
|<span data-ttu-id="625e2-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="625e2-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="625e2-417">Int16</span><span class="sxs-lookup"><span data-stu-id="625e2-417">Int16</span></span>|  
|<span data-ttu-id="625e2-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="625e2-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="625e2-419">String</span><span class="sxs-lookup"><span data-stu-id="625e2-419">String</span></span>|  
|<span data-ttu-id="625e2-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="625e2-420">DESCRIPTION</span></span>|<span data-ttu-id="625e2-421">String</span><span class="sxs-lookup"><span data-stu-id="625e2-421">String</span></span>|  
|<span data-ttu-id="625e2-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="625e2-422">DATE_CREATED</span></span>|<span data-ttu-id="625e2-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="625e2-423">DateTime</span></span>|  
|<span data-ttu-id="625e2-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="625e2-424">DATE_MODIFIED</span></span>|<span data-ttu-id="625e2-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="625e2-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="625e2-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="625e2-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="625e2-427">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="625e2-427">ColumnName</span></span>|<span data-ttu-id="625e2-428">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="625e2-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="625e2-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="625e2-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="625e2-430">String</span><span class="sxs-lookup"><span data-stu-id="625e2-430">String</span></span>|  
|<span data-ttu-id="625e2-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="625e2-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="625e2-432">String</span><span class="sxs-lookup"><span data-stu-id="625e2-432">String</span></span>|  
|<span data-ttu-id="625e2-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="625e2-434">String</span><span class="sxs-lookup"><span data-stu-id="625e2-434">String</span></span>|  
|<span data-ttu-id="625e2-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-435">COLUMN_NAME</span></span>|<span data-ttu-id="625e2-436">String</span><span class="sxs-lookup"><span data-stu-id="625e2-436">String</span></span>|  
|<span data-ttu-id="625e2-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="625e2-437">COLUMN_GUID</span></span>|<span data-ttu-id="625e2-438">Guid</span><span class="sxs-lookup"><span data-stu-id="625e2-438">Guid</span></span>|  
|<span data-ttu-id="625e2-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="625e2-439">COLUMN_PROPID</span></span>|<span data-ttu-id="625e2-440">Int64</span><span class="sxs-lookup"><span data-stu-id="625e2-440">Int64</span></span>|  
|<span data-ttu-id="625e2-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="625e2-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="625e2-442">Int64</span><span class="sxs-lookup"><span data-stu-id="625e2-442">Int64</span></span>|  
|<span data-ttu-id="625e2-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="625e2-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="625e2-444">Int64</span><span class="sxs-lookup"><span data-stu-id="625e2-444">Int64</span></span>|  
|<span data-ttu-id="625e2-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="625e2-445">IS_NULLABLE</span></span>|<span data-ttu-id="625e2-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="625e2-446">Boolean</span></span>|  
|<span data-ttu-id="625e2-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="625e2-447">DATA_TYPE</span></span>|<span data-ttu-id="625e2-448">Int32</span><span class="sxs-lookup"><span data-stu-id="625e2-448">Int32</span></span>|  
|<span data-ttu-id="625e2-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="625e2-449">TYPE_GUID</span></span>|<span data-ttu-id="625e2-450">Guid</span><span class="sxs-lookup"><span data-stu-id="625e2-450">Guid</span></span>|  
|<span data-ttu-id="625e2-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="625e2-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="625e2-452">Int64</span><span class="sxs-lookup"><span data-stu-id="625e2-452">Int64</span></span>|  
|<span data-ttu-id="625e2-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="625e2-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="625e2-454">Int64</span><span class="sxs-lookup"><span data-stu-id="625e2-454">Int64</span></span>|  
|<span data-ttu-id="625e2-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="625e2-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="625e2-456">Int32</span><span class="sxs-lookup"><span data-stu-id="625e2-456">Int32</span></span>|  
|<span data-ttu-id="625e2-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="625e2-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="625e2-458">Int16</span><span class="sxs-lookup"><span data-stu-id="625e2-458">Int16</span></span>|  
|<span data-ttu-id="625e2-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="625e2-459">DESCRIPTION</span></span>|<span data-ttu-id="625e2-460">String</span><span class="sxs-lookup"><span data-stu-id="625e2-460">String</span></span>|  
|<span data-ttu-id="625e2-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="625e2-461">OVERLOAD</span></span>|<span data-ttu-id="625e2-462">Int16</span><span class="sxs-lookup"><span data-stu-id="625e2-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="625e2-463">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="625e2-463">Views</span></span>  
  
|<span data-ttu-id="625e2-464">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="625e2-464">ColumnName</span></span>|<span data-ttu-id="625e2-465">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="625e2-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="625e2-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="625e2-466">TABLE_CATALOG</span></span>|<span data-ttu-id="625e2-467">String</span><span class="sxs-lookup"><span data-stu-id="625e2-467">String</span></span>|  
|<span data-ttu-id="625e2-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="625e2-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="625e2-469">String</span><span class="sxs-lookup"><span data-stu-id="625e2-469">String</span></span>|  
|<span data-ttu-id="625e2-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-470">TABLE_NAME</span></span>|<span data-ttu-id="625e2-471">String</span><span class="sxs-lookup"><span data-stu-id="625e2-471">String</span></span>|  
|<span data-ttu-id="625e2-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="625e2-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="625e2-473">String</span><span class="sxs-lookup"><span data-stu-id="625e2-473">String</span></span>|  
|<span data-ttu-id="625e2-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="625e2-474">CHECK_OPTION</span></span>|<span data-ttu-id="625e2-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="625e2-475">Boolean</span></span>|  
|<span data-ttu-id="625e2-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="625e2-476">IS_UPDATABLE</span></span>|<span data-ttu-id="625e2-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="625e2-477">Boolean</span></span>|  
|<span data-ttu-id="625e2-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="625e2-478">DESCRIPTION</span></span>|<span data-ttu-id="625e2-479">String</span><span class="sxs-lookup"><span data-stu-id="625e2-479">String</span></span>|  
|<span data-ttu-id="625e2-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="625e2-480">DATE_CREATED</span></span>|<span data-ttu-id="625e2-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="625e2-481">DateTime</span></span>|  
|<span data-ttu-id="625e2-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="625e2-482">DATE_MODIFIED</span></span>|<span data-ttu-id="625e2-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="625e2-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="625e2-484">Indexes</span><span class="sxs-lookup"><span data-stu-id="625e2-484">Indexes</span></span>  
  
|<span data-ttu-id="625e2-485">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="625e2-485">ColumnName</span></span>|<span data-ttu-id="625e2-486">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="625e2-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="625e2-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="625e2-487">TABLE_CATALOG</span></span>|<span data-ttu-id="625e2-488">String</span><span class="sxs-lookup"><span data-stu-id="625e2-488">String</span></span>|  
|<span data-ttu-id="625e2-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="625e2-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="625e2-490">String</span><span class="sxs-lookup"><span data-stu-id="625e2-490">String</span></span>|  
|<span data-ttu-id="625e2-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-491">TABLE_NAME</span></span>|<span data-ttu-id="625e2-492">String</span><span class="sxs-lookup"><span data-stu-id="625e2-492">String</span></span>|  
|<span data-ttu-id="625e2-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="625e2-493">INDEX_CATALOG</span></span>|<span data-ttu-id="625e2-494">String</span><span class="sxs-lookup"><span data-stu-id="625e2-494">String</span></span>|  
|<span data-ttu-id="625e2-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="625e2-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="625e2-496">String</span><span class="sxs-lookup"><span data-stu-id="625e2-496">String</span></span>|  
|<span data-ttu-id="625e2-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-497">INDEX_NAME</span></span>|<span data-ttu-id="625e2-498">String</span><span class="sxs-lookup"><span data-stu-id="625e2-498">String</span></span>|  
|<span data-ttu-id="625e2-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="625e2-499">PRIMARY_KEY</span></span>|<span data-ttu-id="625e2-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="625e2-500">Boolean</span></span>|  
|<span data-ttu-id="625e2-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="625e2-501">UNIQUE</span></span>|<span data-ttu-id="625e2-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="625e2-502">Boolean</span></span>|  
|<span data-ttu-id="625e2-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="625e2-503">CLUSTERED</span></span>|<span data-ttu-id="625e2-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="625e2-504">Boolean</span></span>|  
|<span data-ttu-id="625e2-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="625e2-505">TYPE</span></span>|<span data-ttu-id="625e2-506">Int32</span><span class="sxs-lookup"><span data-stu-id="625e2-506">Int32</span></span>|  
|<span data-ttu-id="625e2-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="625e2-507">FILL_FACTOR</span></span>|<span data-ttu-id="625e2-508">Int32</span><span class="sxs-lookup"><span data-stu-id="625e2-508">Int32</span></span>|  
|<span data-ttu-id="625e2-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="625e2-509">INITIAL_SIZE</span></span>|<span data-ttu-id="625e2-510">Int32</span><span class="sxs-lookup"><span data-stu-id="625e2-510">Int32</span></span>|  
|<span data-ttu-id="625e2-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="625e2-511">NULLS</span></span>|<span data-ttu-id="625e2-512">Int32</span><span class="sxs-lookup"><span data-stu-id="625e2-512">Int32</span></span>|  
|<span data-ttu-id="625e2-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="625e2-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="625e2-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="625e2-514">Boolean</span></span>|  
|<span data-ttu-id="625e2-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="625e2-515">AUTO_UPDATE</span></span>|<span data-ttu-id="625e2-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="625e2-516">Boolean</span></span>|  
|<span data-ttu-id="625e2-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="625e2-517">NULL_COLLATION</span></span>|<span data-ttu-id="625e2-518">Int32</span><span class="sxs-lookup"><span data-stu-id="625e2-518">Int32</span></span>|  
|<span data-ttu-id="625e2-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="625e2-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="625e2-520">Int64</span><span class="sxs-lookup"><span data-stu-id="625e2-520">Int64</span></span>|  
|<span data-ttu-id="625e2-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-521">COLUMN_NAME</span></span>|<span data-ttu-id="625e2-522">String</span><span class="sxs-lookup"><span data-stu-id="625e2-522">String</span></span>|  
|<span data-ttu-id="625e2-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="625e2-523">COLUMN_GUID</span></span>|<span data-ttu-id="625e2-524">Guid</span><span class="sxs-lookup"><span data-stu-id="625e2-524">Guid</span></span>|  
|<span data-ttu-id="625e2-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="625e2-525">COLUMN_PROPID</span></span>|<span data-ttu-id="625e2-526">Int64</span><span class="sxs-lookup"><span data-stu-id="625e2-526">Int64</span></span>|  
|<span data-ttu-id="625e2-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="625e2-527">COLLATION</span></span>|<span data-ttu-id="625e2-528">Int16</span><span class="sxs-lookup"><span data-stu-id="625e2-528">Int16</span></span>|  
|<span data-ttu-id="625e2-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="625e2-529">CARDINALITY</span></span>|<span data-ttu-id="625e2-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="625e2-530">Decimal</span></span>|  
|<span data-ttu-id="625e2-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="625e2-531">PAGES</span></span>|<span data-ttu-id="625e2-532">Int32</span><span class="sxs-lookup"><span data-stu-id="625e2-532">Int32</span></span>|  
|<span data-ttu-id="625e2-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="625e2-533">FILTER_CONDITION</span></span>|<span data-ttu-id="625e2-534">String</span><span class="sxs-lookup"><span data-stu-id="625e2-534">String</span></span>|  
|<span data-ttu-id="625e2-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="625e2-535">INTEGRATED</span></span>|<span data-ttu-id="625e2-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="625e2-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="625e2-537">Provider OLE DB per Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="625e2-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="625e2-538">Oltre alle raccolte di schemi comuni, il driver OLE DB di Microsoft Jet supporta le raccolte di schemi specifici seguenti:</span><span class="sxs-lookup"><span data-stu-id="625e2-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="625e2-539">Tabelle</span><span class="sxs-lookup"><span data-stu-id="625e2-539">Tables</span></span>  
  
-   <span data-ttu-id="625e2-540">Colonne</span><span class="sxs-lookup"><span data-stu-id="625e2-540">Columns</span></span>  
  
-   <span data-ttu-id="625e2-541">Procedure</span><span class="sxs-lookup"><span data-stu-id="625e2-541">Procedures</span></span>  
  
-   <span data-ttu-id="625e2-542">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="625e2-542">Views</span></span>  
  
-   <span data-ttu-id="625e2-543">Indexes</span><span class="sxs-lookup"><span data-stu-id="625e2-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="625e2-544">Tabelle</span><span class="sxs-lookup"><span data-stu-id="625e2-544">Tables</span></span>  
  
|<span data-ttu-id="625e2-545">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="625e2-545">ColumnName</span></span>|<span data-ttu-id="625e2-546">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="625e2-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="625e2-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="625e2-547">TABLE_CATALOG</span></span>|<span data-ttu-id="625e2-548">String</span><span class="sxs-lookup"><span data-stu-id="625e2-548">String</span></span>|  
|<span data-ttu-id="625e2-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="625e2-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="625e2-550">String</span><span class="sxs-lookup"><span data-stu-id="625e2-550">String</span></span>|  
|<span data-ttu-id="625e2-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-551">TABLE_NAME</span></span>|<span data-ttu-id="625e2-552">String</span><span class="sxs-lookup"><span data-stu-id="625e2-552">String</span></span>|  
|<span data-ttu-id="625e2-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="625e2-553">TABLE_TYPE</span></span>|<span data-ttu-id="625e2-554">String</span><span class="sxs-lookup"><span data-stu-id="625e2-554">String</span></span>|  
|<span data-ttu-id="625e2-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="625e2-555">TABLE_GUID</span></span>|<span data-ttu-id="625e2-556">Guid</span><span class="sxs-lookup"><span data-stu-id="625e2-556">Guid</span></span>|  
|<span data-ttu-id="625e2-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="625e2-557">DESCRIPTION</span></span>|<span data-ttu-id="625e2-558">String</span><span class="sxs-lookup"><span data-stu-id="625e2-558">String</span></span>|  
|<span data-ttu-id="625e2-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="625e2-559">TABLE_PROPID</span></span>|<span data-ttu-id="625e2-560">Int64</span><span class="sxs-lookup"><span data-stu-id="625e2-560">Int64</span></span>|  
|<span data-ttu-id="625e2-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="625e2-561">DATE_CREATED</span></span>|<span data-ttu-id="625e2-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="625e2-562">DateTime</span></span>|  
|<span data-ttu-id="625e2-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="625e2-563">DATE_MODIFIED</span></span>|<span data-ttu-id="625e2-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="625e2-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="625e2-565">Colonne</span><span class="sxs-lookup"><span data-stu-id="625e2-565">Columns</span></span>  
  
|<span data-ttu-id="625e2-566">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="625e2-566">ColumnName</span></span>|<span data-ttu-id="625e2-567">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="625e2-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="625e2-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="625e2-568">TABLE_CATALOG</span></span>|<span data-ttu-id="625e2-569">String</span><span class="sxs-lookup"><span data-stu-id="625e2-569">String</span></span>|  
|<span data-ttu-id="625e2-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="625e2-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="625e2-571">String</span><span class="sxs-lookup"><span data-stu-id="625e2-571">String</span></span>|  
|<span data-ttu-id="625e2-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-572">TABLE_NAME</span></span>|<span data-ttu-id="625e2-573">String</span><span class="sxs-lookup"><span data-stu-id="625e2-573">String</span></span>|  
|<span data-ttu-id="625e2-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-574">COLUMN_NAME</span></span>|<span data-ttu-id="625e2-575">String</span><span class="sxs-lookup"><span data-stu-id="625e2-575">String</span></span>|  
|<span data-ttu-id="625e2-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="625e2-576">COLUMN_GUID</span></span>|<span data-ttu-id="625e2-577">Guid</span><span class="sxs-lookup"><span data-stu-id="625e2-577">Guid</span></span>|  
|<span data-ttu-id="625e2-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="625e2-578">COLUMN_PROPID</span></span>|<span data-ttu-id="625e2-579">Int64</span><span class="sxs-lookup"><span data-stu-id="625e2-579">Int64</span></span>|  
|<span data-ttu-id="625e2-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="625e2-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="625e2-581">Int64</span><span class="sxs-lookup"><span data-stu-id="625e2-581">Int64</span></span>|  
|<span data-ttu-id="625e2-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="625e2-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="625e2-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="625e2-583">Boolean</span></span>|  
|<span data-ttu-id="625e2-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="625e2-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="625e2-585">String</span><span class="sxs-lookup"><span data-stu-id="625e2-585">String</span></span>|  
|<span data-ttu-id="625e2-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="625e2-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="625e2-587">Int64</span><span class="sxs-lookup"><span data-stu-id="625e2-587">Int64</span></span>|  
|<span data-ttu-id="625e2-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="625e2-588">IS_NULLABLE</span></span>|<span data-ttu-id="625e2-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="625e2-589">Boolean</span></span>|  
|<span data-ttu-id="625e2-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="625e2-590">DATA_TYPE</span></span>|<span data-ttu-id="625e2-591">Int32</span><span class="sxs-lookup"><span data-stu-id="625e2-591">Int32</span></span>|  
|<span data-ttu-id="625e2-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="625e2-592">TYPE_GUID</span></span>|<span data-ttu-id="625e2-593">Guid</span><span class="sxs-lookup"><span data-stu-id="625e2-593">Guid</span></span>|  
|<span data-ttu-id="625e2-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="625e2-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="625e2-595">Int64</span><span class="sxs-lookup"><span data-stu-id="625e2-595">Int64</span></span>|  
|<span data-ttu-id="625e2-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="625e2-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="625e2-597">Int64</span><span class="sxs-lookup"><span data-stu-id="625e2-597">Int64</span></span>|  
|<span data-ttu-id="625e2-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="625e2-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="625e2-599">Int32</span><span class="sxs-lookup"><span data-stu-id="625e2-599">Int32</span></span>|  
|<span data-ttu-id="625e2-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="625e2-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="625e2-601">Int16</span><span class="sxs-lookup"><span data-stu-id="625e2-601">Int16</span></span>|  
|<span data-ttu-id="625e2-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="625e2-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="625e2-603">Int64</span><span class="sxs-lookup"><span data-stu-id="625e2-603">Int64</span></span>|  
|<span data-ttu-id="625e2-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="625e2-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="625e2-605">String</span><span class="sxs-lookup"><span data-stu-id="625e2-605">String</span></span>|  
|<span data-ttu-id="625e2-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="625e2-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="625e2-607">String</span><span class="sxs-lookup"><span data-stu-id="625e2-607">String</span></span>|  
|<span data-ttu-id="625e2-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="625e2-609">String</span><span class="sxs-lookup"><span data-stu-id="625e2-609">String</span></span>|  
|<span data-ttu-id="625e2-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="625e2-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="625e2-611">String</span><span class="sxs-lookup"><span data-stu-id="625e2-611">String</span></span>|  
|<span data-ttu-id="625e2-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="625e2-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="625e2-613">String</span><span class="sxs-lookup"><span data-stu-id="625e2-613">String</span></span>|  
|<span data-ttu-id="625e2-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-614">COLLATION_NAME</span></span>|<span data-ttu-id="625e2-615">String</span><span class="sxs-lookup"><span data-stu-id="625e2-615">String</span></span>|  
|<span data-ttu-id="625e2-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="625e2-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="625e2-617">String</span><span class="sxs-lookup"><span data-stu-id="625e2-617">String</span></span>|  
|<span data-ttu-id="625e2-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="625e2-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="625e2-619">String</span><span class="sxs-lookup"><span data-stu-id="625e2-619">String</span></span>|  
|<span data-ttu-id="625e2-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-620">DOMAIN_NAME</span></span>|<span data-ttu-id="625e2-621">String</span><span class="sxs-lookup"><span data-stu-id="625e2-621">String</span></span>|  
|<span data-ttu-id="625e2-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="625e2-622">DESCRIPTION</span></span>|<span data-ttu-id="625e2-623">String</span><span class="sxs-lookup"><span data-stu-id="625e2-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="625e2-624">Procedure</span><span class="sxs-lookup"><span data-stu-id="625e2-624">Procedures</span></span>  
  
|<span data-ttu-id="625e2-625">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="625e2-625">ColumnName</span></span>|<span data-ttu-id="625e2-626">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="625e2-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="625e2-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="625e2-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="625e2-628">String</span><span class="sxs-lookup"><span data-stu-id="625e2-628">String</span></span>|  
|<span data-ttu-id="625e2-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="625e2-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="625e2-630">String</span><span class="sxs-lookup"><span data-stu-id="625e2-630">String</span></span>|  
|<span data-ttu-id="625e2-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="625e2-632">String</span><span class="sxs-lookup"><span data-stu-id="625e2-632">String</span></span>|  
|<span data-ttu-id="625e2-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="625e2-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="625e2-634">Int16</span><span class="sxs-lookup"><span data-stu-id="625e2-634">Int16</span></span>|  
|<span data-ttu-id="625e2-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="625e2-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="625e2-636">String</span><span class="sxs-lookup"><span data-stu-id="625e2-636">String</span></span>|  
|<span data-ttu-id="625e2-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="625e2-637">DESCRIPTION</span></span>|<span data-ttu-id="625e2-638">String</span><span class="sxs-lookup"><span data-stu-id="625e2-638">String</span></span>|  
|<span data-ttu-id="625e2-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="625e2-639">DATE_CREATED</span></span>|<span data-ttu-id="625e2-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="625e2-640">DateTime</span></span>|  
|<span data-ttu-id="625e2-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="625e2-641">DATE_MODIFIED</span></span>|<span data-ttu-id="625e2-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="625e2-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="625e2-643">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="625e2-643">Views</span></span>  
  
|<span data-ttu-id="625e2-644">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="625e2-644">ColumnName</span></span>|<span data-ttu-id="625e2-645">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="625e2-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="625e2-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="625e2-646">TABLE_CATALOG</span></span>|<span data-ttu-id="625e2-647">String</span><span class="sxs-lookup"><span data-stu-id="625e2-647">String</span></span>|  
|<span data-ttu-id="625e2-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="625e2-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="625e2-649">String</span><span class="sxs-lookup"><span data-stu-id="625e2-649">String</span></span>|  
|<span data-ttu-id="625e2-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-650">TABLE_NAME</span></span>|<span data-ttu-id="625e2-651">String</span><span class="sxs-lookup"><span data-stu-id="625e2-651">String</span></span>|  
|<span data-ttu-id="625e2-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="625e2-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="625e2-653">String</span><span class="sxs-lookup"><span data-stu-id="625e2-653">String</span></span>|  
|<span data-ttu-id="625e2-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="625e2-654">CHECK_OPTION</span></span>|<span data-ttu-id="625e2-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="625e2-655">Boolean</span></span>|  
|<span data-ttu-id="625e2-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="625e2-656">IS_UPDATABLE</span></span>|<span data-ttu-id="625e2-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="625e2-657">Boolean</span></span>|  
|<span data-ttu-id="625e2-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="625e2-658">DESCRIPTION</span></span>|<span data-ttu-id="625e2-659">String</span><span class="sxs-lookup"><span data-stu-id="625e2-659">String</span></span>|  
|<span data-ttu-id="625e2-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="625e2-660">DATE_CREATED</span></span>|<span data-ttu-id="625e2-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="625e2-661">DateTime</span></span>|  
|<span data-ttu-id="625e2-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="625e2-662">DATE_MODIFIED</span></span>|<span data-ttu-id="625e2-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="625e2-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="625e2-664">Indexes</span><span class="sxs-lookup"><span data-stu-id="625e2-664">Indexes</span></span>  
  
|<span data-ttu-id="625e2-665">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="625e2-665">ColumnName</span></span>|<span data-ttu-id="625e2-666">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="625e2-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="625e2-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="625e2-667">TABLE_CATALOG</span></span>|<span data-ttu-id="625e2-668">String</span><span class="sxs-lookup"><span data-stu-id="625e2-668">String</span></span>|  
|<span data-ttu-id="625e2-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="625e2-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="625e2-670">String</span><span class="sxs-lookup"><span data-stu-id="625e2-670">String</span></span>|  
|<span data-ttu-id="625e2-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-671">TABLE_NAME</span></span>|<span data-ttu-id="625e2-672">String</span><span class="sxs-lookup"><span data-stu-id="625e2-672">String</span></span>|  
|<span data-ttu-id="625e2-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="625e2-673">INDEX_CATALOG</span></span>|<span data-ttu-id="625e2-674">String</span><span class="sxs-lookup"><span data-stu-id="625e2-674">String</span></span>|  
|<span data-ttu-id="625e2-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="625e2-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="625e2-676">String</span><span class="sxs-lookup"><span data-stu-id="625e2-676">String</span></span>|  
|<span data-ttu-id="625e2-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-677">INDEX_NAME</span></span>|<span data-ttu-id="625e2-678">String</span><span class="sxs-lookup"><span data-stu-id="625e2-678">String</span></span>|  
|<span data-ttu-id="625e2-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="625e2-679">PRIMARY_KEY</span></span>|<span data-ttu-id="625e2-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="625e2-680">Boolean</span></span>|  
|<span data-ttu-id="625e2-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="625e2-681">UNIQUE</span></span>|<span data-ttu-id="625e2-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="625e2-682">Boolean</span></span>|  
|<span data-ttu-id="625e2-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="625e2-683">CLUSTERED</span></span>|<span data-ttu-id="625e2-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="625e2-684">Boolean</span></span>|  
|<span data-ttu-id="625e2-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="625e2-685">TYPE</span></span>|<span data-ttu-id="625e2-686">Int32</span><span class="sxs-lookup"><span data-stu-id="625e2-686">Int32</span></span>|  
|<span data-ttu-id="625e2-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="625e2-687">FILL_FACTOR</span></span>|<span data-ttu-id="625e2-688">Int32</span><span class="sxs-lookup"><span data-stu-id="625e2-688">Int32</span></span>|  
|<span data-ttu-id="625e2-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="625e2-689">INITIAL_SIZE</span></span>|<span data-ttu-id="625e2-690">Int32</span><span class="sxs-lookup"><span data-stu-id="625e2-690">Int32</span></span>|  
|<span data-ttu-id="625e2-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="625e2-691">NULLS</span></span>|<span data-ttu-id="625e2-692">Int32</span><span class="sxs-lookup"><span data-stu-id="625e2-692">Int32</span></span>|  
|<span data-ttu-id="625e2-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="625e2-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="625e2-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="625e2-694">Boolean</span></span>|  
|<span data-ttu-id="625e2-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="625e2-695">AUTO_UPDATE</span></span>|<span data-ttu-id="625e2-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="625e2-696">Boolean</span></span>|  
|<span data-ttu-id="625e2-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="625e2-697">NULL_COLLATION</span></span>|<span data-ttu-id="625e2-698">Int32</span><span class="sxs-lookup"><span data-stu-id="625e2-698">Int32</span></span>|  
|<span data-ttu-id="625e2-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="625e2-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="625e2-700">Int64</span><span class="sxs-lookup"><span data-stu-id="625e2-700">Int64</span></span>|  
|<span data-ttu-id="625e2-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="625e2-701">COLUMN_NAME</span></span>|<span data-ttu-id="625e2-702">String</span><span class="sxs-lookup"><span data-stu-id="625e2-702">String</span></span>|  
|<span data-ttu-id="625e2-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="625e2-703">COLUMN_GUID</span></span>|<span data-ttu-id="625e2-704">Guid</span><span class="sxs-lookup"><span data-stu-id="625e2-704">Guid</span></span>|  
|<span data-ttu-id="625e2-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="625e2-705">COLUMN_PROPID</span></span>|<span data-ttu-id="625e2-706">Int64</span><span class="sxs-lookup"><span data-stu-id="625e2-706">Int64</span></span>|  
|<span data-ttu-id="625e2-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="625e2-707">COLLATION</span></span>|<span data-ttu-id="625e2-708">Int16</span><span class="sxs-lookup"><span data-stu-id="625e2-708">Int16</span></span>|  
|<span data-ttu-id="625e2-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="625e2-709">CARDINALITY</span></span>|<span data-ttu-id="625e2-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="625e2-710">Decimal</span></span>|  
|<span data-ttu-id="625e2-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="625e2-711">PAGES</span></span>|<span data-ttu-id="625e2-712">Int32</span><span class="sxs-lookup"><span data-stu-id="625e2-712">Int32</span></span>|  
|<span data-ttu-id="625e2-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="625e2-713">FILTER_CONDITION</span></span>|<span data-ttu-id="625e2-714">String</span><span class="sxs-lookup"><span data-stu-id="625e2-714">String</span></span>|  
|<span data-ttu-id="625e2-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="625e2-715">INTEGRATED</span></span>|<span data-ttu-id="625e2-716">Booleano</span><span class="sxs-lookup"><span data-stu-id="625e2-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="625e2-717">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="625e2-717">See Also</span></span>  
 [<span data-ttu-id="625e2-718">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="625e2-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
