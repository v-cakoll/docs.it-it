---
title: Raccolte di schemi OLE DB
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 1ab6426875b73b400a59b7e4cf155615d7472d05
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43514489"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="109dd-102">Raccolte di schemi OLE DB</span><span class="sxs-lookup"><span data-stu-id="109dd-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="109dd-103">Contenuto della sezione viene descritto il supporto delle raccolte di schemi per i provider OLE DB per Microsoft SQL Server, Oracle e Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="109dd-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="109dd-104">Provider OLE DB per Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="109dd-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="109dd-105">Il Driver OLE DB Microsoft SQL Server supporta le seguenti raccolte di schemi specifici oltre alle raccolte di schemi comuni:</span><span class="sxs-lookup"><span data-stu-id="109dd-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="109dd-106">Tabelle</span><span class="sxs-lookup"><span data-stu-id="109dd-106">Tables</span></span>  
  
-   <span data-ttu-id="109dd-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="109dd-107">Columns</span></span>  
  
-   <span data-ttu-id="109dd-108">Procedure</span><span class="sxs-lookup"><span data-stu-id="109dd-108">Procedures</span></span>  
  
-   <span data-ttu-id="109dd-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="109dd-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="109dd-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="109dd-110">Catalog</span></span>  
  
-   <span data-ttu-id="109dd-111">Indexes</span><span class="sxs-lookup"><span data-stu-id="109dd-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="109dd-112">Tabelle</span><span class="sxs-lookup"><span data-stu-id="109dd-112">Tables</span></span>  
  
|<span data-ttu-id="109dd-113">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="109dd-113">ColumnName</span></span>|<span data-ttu-id="109dd-114">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="109dd-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="109dd-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="109dd-115">TABLE_CATALOG</span></span>|<span data-ttu-id="109dd-116">String</span><span class="sxs-lookup"><span data-stu-id="109dd-116">String</span></span>|  
|<span data-ttu-id="109dd-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="109dd-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="109dd-118">String</span><span class="sxs-lookup"><span data-stu-id="109dd-118">String</span></span>|  
|<span data-ttu-id="109dd-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-119">TABLE_NAME</span></span>|<span data-ttu-id="109dd-120">String</span><span class="sxs-lookup"><span data-stu-id="109dd-120">String</span></span>|  
|<span data-ttu-id="109dd-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="109dd-121">TABLE_TYPE</span></span>|<span data-ttu-id="109dd-122">String</span><span class="sxs-lookup"><span data-stu-id="109dd-122">String</span></span>|  
|<span data-ttu-id="109dd-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="109dd-123">TABLE_GUID</span></span>|<span data-ttu-id="109dd-124">Guid</span><span class="sxs-lookup"><span data-stu-id="109dd-124">Guid</span></span>|  
|<span data-ttu-id="109dd-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="109dd-125">DESCRIPTION</span></span>|<span data-ttu-id="109dd-126">String</span><span class="sxs-lookup"><span data-stu-id="109dd-126">String</span></span>|  
|<span data-ttu-id="109dd-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="109dd-127">TABLE_PROPID</span></span>|<span data-ttu-id="109dd-128">Int64</span><span class="sxs-lookup"><span data-stu-id="109dd-128">Int64</span></span>|  
|<span data-ttu-id="109dd-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="109dd-129">DATE_CREATED</span></span>|<span data-ttu-id="109dd-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="109dd-130">DateTime</span></span>|  
|<span data-ttu-id="109dd-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="109dd-131">DATE_MODIFIED</span></span>|<span data-ttu-id="109dd-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="109dd-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="109dd-133">Colonne</span><span class="sxs-lookup"><span data-stu-id="109dd-133">Columns</span></span>  
  
|<span data-ttu-id="109dd-134">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="109dd-134">ColumnName</span></span>|<span data-ttu-id="109dd-135">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="109dd-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="109dd-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="109dd-136">TABLE_CATALOG</span></span>|<span data-ttu-id="109dd-137">String</span><span class="sxs-lookup"><span data-stu-id="109dd-137">String</span></span>|  
|<span data-ttu-id="109dd-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="109dd-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="109dd-139">String</span><span class="sxs-lookup"><span data-stu-id="109dd-139">String</span></span>|  
|<span data-ttu-id="109dd-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-140">TABLE_NAME</span></span>|<span data-ttu-id="109dd-141">String</span><span class="sxs-lookup"><span data-stu-id="109dd-141">String</span></span>|  
|<span data-ttu-id="109dd-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-142">COLUMN_NAME</span></span>|<span data-ttu-id="109dd-143">String</span><span class="sxs-lookup"><span data-stu-id="109dd-143">String</span></span>|  
|<span data-ttu-id="109dd-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="109dd-144">COLUMN_GUID</span></span>|<span data-ttu-id="109dd-145">Guid</span><span class="sxs-lookup"><span data-stu-id="109dd-145">Guid</span></span>|  
|<span data-ttu-id="109dd-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="109dd-146">COLUMN_PROPID</span></span>|<span data-ttu-id="109dd-147">Int64</span><span class="sxs-lookup"><span data-stu-id="109dd-147">Int64</span></span>|  
|<span data-ttu-id="109dd-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="109dd-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="109dd-149">Int64</span><span class="sxs-lookup"><span data-stu-id="109dd-149">Int64</span></span>|  
|<span data-ttu-id="109dd-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="109dd-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="109dd-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="109dd-151">Boolean</span></span>|  
|<span data-ttu-id="109dd-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="109dd-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="109dd-153">String</span><span class="sxs-lookup"><span data-stu-id="109dd-153">String</span></span>|  
|<span data-ttu-id="109dd-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="109dd-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="109dd-155">Int64</span><span class="sxs-lookup"><span data-stu-id="109dd-155">Int64</span></span>|  
|<span data-ttu-id="109dd-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="109dd-156">IS_NULLABLE</span></span>|<span data-ttu-id="109dd-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="109dd-157">Boolean</span></span>|  
|<span data-ttu-id="109dd-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="109dd-158">DATA_TYPE</span></span>|<span data-ttu-id="109dd-159">Int32</span><span class="sxs-lookup"><span data-stu-id="109dd-159">Int32</span></span>|  
|<span data-ttu-id="109dd-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="109dd-160">TYPE_GUID</span></span>|<span data-ttu-id="109dd-161">Guid</span><span class="sxs-lookup"><span data-stu-id="109dd-161">Guid</span></span>|  
|<span data-ttu-id="109dd-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="109dd-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="109dd-163">Int64</span><span class="sxs-lookup"><span data-stu-id="109dd-163">Int64</span></span>|  
|<span data-ttu-id="109dd-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="109dd-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="109dd-165">Int64</span><span class="sxs-lookup"><span data-stu-id="109dd-165">Int64</span></span>|  
|<span data-ttu-id="109dd-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="109dd-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="109dd-167">Int32</span><span class="sxs-lookup"><span data-stu-id="109dd-167">Int32</span></span>|  
|<span data-ttu-id="109dd-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="109dd-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="109dd-169">Int16</span><span class="sxs-lookup"><span data-stu-id="109dd-169">Int16</span></span>|  
|<span data-ttu-id="109dd-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="109dd-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="109dd-171">Int64</span><span class="sxs-lookup"><span data-stu-id="109dd-171">Int64</span></span>|  
|<span data-ttu-id="109dd-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="109dd-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="109dd-173">String</span><span class="sxs-lookup"><span data-stu-id="109dd-173">String</span></span>|  
|<span data-ttu-id="109dd-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="109dd-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="109dd-175">String</span><span class="sxs-lookup"><span data-stu-id="109dd-175">String</span></span>|  
|<span data-ttu-id="109dd-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="109dd-177">String</span><span class="sxs-lookup"><span data-stu-id="109dd-177">String</span></span>|  
|<span data-ttu-id="109dd-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="109dd-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="109dd-179">String</span><span class="sxs-lookup"><span data-stu-id="109dd-179">String</span></span>|  
|<span data-ttu-id="109dd-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="109dd-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="109dd-181">String</span><span class="sxs-lookup"><span data-stu-id="109dd-181">String</span></span>|  
|<span data-ttu-id="109dd-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-182">COLLATION_NAME</span></span>|<span data-ttu-id="109dd-183">String</span><span class="sxs-lookup"><span data-stu-id="109dd-183">String</span></span>|  
|<span data-ttu-id="109dd-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="109dd-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="109dd-185">String</span><span class="sxs-lookup"><span data-stu-id="109dd-185">String</span></span>|  
|<span data-ttu-id="109dd-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="109dd-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="109dd-187">String</span><span class="sxs-lookup"><span data-stu-id="109dd-187">String</span></span>|  
|<span data-ttu-id="109dd-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-188">DOMAIN_NAME</span></span>|<span data-ttu-id="109dd-189">String</span><span class="sxs-lookup"><span data-stu-id="109dd-189">String</span></span>|  
|<span data-ttu-id="109dd-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="109dd-190">DESCRIPTION</span></span>|<span data-ttu-id="109dd-191">String</span><span class="sxs-lookup"><span data-stu-id="109dd-191">String</span></span>|  
|<span data-ttu-id="109dd-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="109dd-192">COLUMN_LCID</span></span>|<span data-ttu-id="109dd-193">Int32</span><span class="sxs-lookup"><span data-stu-id="109dd-193">Int32</span></span>|  
|<span data-ttu-id="109dd-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="109dd-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="109dd-195">Int32</span><span class="sxs-lookup"><span data-stu-id="109dd-195">Int32</span></span>|  
|<span data-ttu-id="109dd-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="109dd-196">COLUMN_SORTID</span></span>|<span data-ttu-id="109dd-197">Int32</span><span class="sxs-lookup"><span data-stu-id="109dd-197">Int32</span></span>|  
|<span data-ttu-id="109dd-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="109dd-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="109dd-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="109dd-199">Byte[]</span></span>|  
|<span data-ttu-id="109dd-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="109dd-200">IS_COMPUTED</span></span>|<span data-ttu-id="109dd-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="109dd-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="109dd-202">Procedure</span><span class="sxs-lookup"><span data-stu-id="109dd-202">Procedures</span></span>  
  
|<span data-ttu-id="109dd-203">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="109dd-203">ColumnName</span></span>|<span data-ttu-id="109dd-204">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="109dd-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="109dd-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="109dd-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="109dd-206">String</span><span class="sxs-lookup"><span data-stu-id="109dd-206">String</span></span>|  
|<span data-ttu-id="109dd-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="109dd-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="109dd-208">String</span><span class="sxs-lookup"><span data-stu-id="109dd-208">String</span></span>|  
|<span data-ttu-id="109dd-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="109dd-210">String</span><span class="sxs-lookup"><span data-stu-id="109dd-210">String</span></span>|  
|<span data-ttu-id="109dd-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="109dd-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="109dd-212">Int16</span><span class="sxs-lookup"><span data-stu-id="109dd-212">Int16</span></span>|  
|<span data-ttu-id="109dd-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="109dd-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="109dd-214">String</span><span class="sxs-lookup"><span data-stu-id="109dd-214">String</span></span>|  
|<span data-ttu-id="109dd-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="109dd-215">DESCRIPTION</span></span>|<span data-ttu-id="109dd-216">String</span><span class="sxs-lookup"><span data-stu-id="109dd-216">String</span></span>|  
|<span data-ttu-id="109dd-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="109dd-217">DATE_CREATED</span></span>|<span data-ttu-id="109dd-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="109dd-218">DateTime</span></span>|  
|<span data-ttu-id="109dd-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="109dd-219">DATE_MODIFIED</span></span>|<span data-ttu-id="109dd-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="109dd-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="109dd-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="109dd-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="109dd-222">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="109dd-222">ColumnName</span></span>|<span data-ttu-id="109dd-223">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="109dd-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="109dd-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="109dd-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="109dd-225">String</span><span class="sxs-lookup"><span data-stu-id="109dd-225">String</span></span>|  
|<span data-ttu-id="109dd-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="109dd-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="109dd-227">String</span><span class="sxs-lookup"><span data-stu-id="109dd-227">String</span></span>|  
|<span data-ttu-id="109dd-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="109dd-229">String</span><span class="sxs-lookup"><span data-stu-id="109dd-229">String</span></span>|  
|<span data-ttu-id="109dd-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-230">PARAMETER_NAME</span></span>|<span data-ttu-id="109dd-231">String</span><span class="sxs-lookup"><span data-stu-id="109dd-231">String</span></span>|  
|<span data-ttu-id="109dd-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="109dd-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="109dd-233">Int32</span><span class="sxs-lookup"><span data-stu-id="109dd-233">Int32</span></span>|  
|<span data-ttu-id="109dd-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="109dd-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="109dd-235">Int32</span><span class="sxs-lookup"><span data-stu-id="109dd-235">Int32</span></span>|  
|<span data-ttu-id="109dd-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="109dd-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="109dd-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="109dd-237">Boolean</span></span>|  
|<span data-ttu-id="109dd-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="109dd-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="109dd-239">String</span><span class="sxs-lookup"><span data-stu-id="109dd-239">String</span></span>|  
|<span data-ttu-id="109dd-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="109dd-240">IS_NULLABLE</span></span>|<span data-ttu-id="109dd-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="109dd-241">Boolean</span></span>|  
|<span data-ttu-id="109dd-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="109dd-242">DATA_TYPE</span></span>|<span data-ttu-id="109dd-243">Int32</span><span class="sxs-lookup"><span data-stu-id="109dd-243">Int32</span></span>|  
|<span data-ttu-id="109dd-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="109dd-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="109dd-245">Int64</span><span class="sxs-lookup"><span data-stu-id="109dd-245">Int64</span></span>|  
|<span data-ttu-id="109dd-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="109dd-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="109dd-247">Int64</span><span class="sxs-lookup"><span data-stu-id="109dd-247">Int64</span></span>|  
|<span data-ttu-id="109dd-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="109dd-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="109dd-249">Int32</span><span class="sxs-lookup"><span data-stu-id="109dd-249">Int32</span></span>|  
|<span data-ttu-id="109dd-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="109dd-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="109dd-251">Int16</span><span class="sxs-lookup"><span data-stu-id="109dd-251">Int16</span></span>|  
|<span data-ttu-id="109dd-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="109dd-252">DESCRIPTION</span></span>|<span data-ttu-id="109dd-253">String</span><span class="sxs-lookup"><span data-stu-id="109dd-253">String</span></span>|  
|<span data-ttu-id="109dd-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-254">TYPE_NAME</span></span>|<span data-ttu-id="109dd-255">String</span><span class="sxs-lookup"><span data-stu-id="109dd-255">String</span></span>|  
|<span data-ttu-id="109dd-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="109dd-257">String</span><span class="sxs-lookup"><span data-stu-id="109dd-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="109dd-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="109dd-258">Catalog</span></span>  
  
|<span data-ttu-id="109dd-259">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="109dd-259">ColumnName</span></span>|<span data-ttu-id="109dd-260">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="109dd-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="109dd-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-261">CATALOG_NAME</span></span>|<span data-ttu-id="109dd-262">String</span><span class="sxs-lookup"><span data-stu-id="109dd-262">String</span></span>|  
|<span data-ttu-id="109dd-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="109dd-263">DESCRIPTION</span></span>|<span data-ttu-id="109dd-264">String</span><span class="sxs-lookup"><span data-stu-id="109dd-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="109dd-265">Indexes</span><span class="sxs-lookup"><span data-stu-id="109dd-265">Indexes</span></span>  
  
|<span data-ttu-id="109dd-266">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="109dd-266">ColumnName</span></span>|<span data-ttu-id="109dd-267">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="109dd-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="109dd-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="109dd-268">TABLE_CATALOG</span></span>|<span data-ttu-id="109dd-269">String</span><span class="sxs-lookup"><span data-stu-id="109dd-269">String</span></span>|  
|<span data-ttu-id="109dd-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="109dd-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="109dd-271">String</span><span class="sxs-lookup"><span data-stu-id="109dd-271">String</span></span>|  
|<span data-ttu-id="109dd-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-272">TABLE_NAME</span></span>|<span data-ttu-id="109dd-273">String</span><span class="sxs-lookup"><span data-stu-id="109dd-273">String</span></span>|  
|<span data-ttu-id="109dd-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="109dd-274">INDEX_CATALOG</span></span>|<span data-ttu-id="109dd-275">String</span><span class="sxs-lookup"><span data-stu-id="109dd-275">String</span></span>|  
|<span data-ttu-id="109dd-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="109dd-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="109dd-277">String</span><span class="sxs-lookup"><span data-stu-id="109dd-277">String</span></span>|  
|<span data-ttu-id="109dd-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-278">INDEX_NAME</span></span>|<span data-ttu-id="109dd-279">String</span><span class="sxs-lookup"><span data-stu-id="109dd-279">String</span></span>|  
|<span data-ttu-id="109dd-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="109dd-280">PRIMARY_KEY</span></span>|<span data-ttu-id="109dd-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="109dd-281">Boolean</span></span>|  
|<span data-ttu-id="109dd-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="109dd-282">UNIQUE</span></span>|<span data-ttu-id="109dd-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="109dd-283">Boolean</span></span>|  
|<span data-ttu-id="109dd-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="109dd-284">CLUSTERED</span></span>|<span data-ttu-id="109dd-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="109dd-285">Boolean</span></span>|  
|<span data-ttu-id="109dd-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="109dd-286">TYPE</span></span>|<span data-ttu-id="109dd-287">Int32</span><span class="sxs-lookup"><span data-stu-id="109dd-287">Int32</span></span>|  
|<span data-ttu-id="109dd-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="109dd-288">FILL_FACTOR</span></span>|<span data-ttu-id="109dd-289">Int32</span><span class="sxs-lookup"><span data-stu-id="109dd-289">Int32</span></span>|  
|<span data-ttu-id="109dd-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="109dd-290">INITIAL_SIZE</span></span>|<span data-ttu-id="109dd-291">Int32</span><span class="sxs-lookup"><span data-stu-id="109dd-291">Int32</span></span>|  
|<span data-ttu-id="109dd-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="109dd-292">NULLS</span></span>|<span data-ttu-id="109dd-293">Int32</span><span class="sxs-lookup"><span data-stu-id="109dd-293">Int32</span></span>|  
|<span data-ttu-id="109dd-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="109dd-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="109dd-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="109dd-295">Boolean</span></span>|  
|<span data-ttu-id="109dd-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="109dd-296">AUTO_UPDATE</span></span>|<span data-ttu-id="109dd-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="109dd-297">Boolean</span></span>|  
|<span data-ttu-id="109dd-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="109dd-298">NULL_COLLATION</span></span>|<span data-ttu-id="109dd-299">Int32</span><span class="sxs-lookup"><span data-stu-id="109dd-299">Int32</span></span>|  
|<span data-ttu-id="109dd-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="109dd-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="109dd-301">Int64</span><span class="sxs-lookup"><span data-stu-id="109dd-301">Int64</span></span>|  
|<span data-ttu-id="109dd-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-302">COLUMN_NAME</span></span>|<span data-ttu-id="109dd-303">String</span><span class="sxs-lookup"><span data-stu-id="109dd-303">String</span></span>|  
|<span data-ttu-id="109dd-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="109dd-304">COLUMN_GUID</span></span>|<span data-ttu-id="109dd-305">Guid</span><span class="sxs-lookup"><span data-stu-id="109dd-305">Guid</span></span>|  
|<span data-ttu-id="109dd-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="109dd-306">COLUMN_PROPID</span></span>|<span data-ttu-id="109dd-307">Int64</span><span class="sxs-lookup"><span data-stu-id="109dd-307">Int64</span></span>|  
|<span data-ttu-id="109dd-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="109dd-308">COLLATION</span></span>|<span data-ttu-id="109dd-309">Int16</span><span class="sxs-lookup"><span data-stu-id="109dd-309">Int16</span></span>|  
|<span data-ttu-id="109dd-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="109dd-310">CARDINALITY</span></span>|<span data-ttu-id="109dd-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="109dd-311">Decimal</span></span>|  
|<span data-ttu-id="109dd-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="109dd-312">PAGES</span></span>|<span data-ttu-id="109dd-313">Int32</span><span class="sxs-lookup"><span data-stu-id="109dd-313">Int32</span></span>|  
|<span data-ttu-id="109dd-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="109dd-314">FILTER_CONDITION</span></span>|<span data-ttu-id="109dd-315">String</span><span class="sxs-lookup"><span data-stu-id="109dd-315">String</span></span>|  
|<span data-ttu-id="109dd-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="109dd-316">INTEGRATED</span></span>|<span data-ttu-id="109dd-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="109dd-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="109dd-318">Provider OLE DB per Microsoft Oracle</span><span class="sxs-lookup"><span data-stu-id="109dd-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="109dd-319">Oltre alle raccolte di schemi comuni, il driver OLE DB per Microsoft Oracle supporta le seguenti raccolte di schemi specifici:</span><span class="sxs-lookup"><span data-stu-id="109dd-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="109dd-320">Tabelle</span><span class="sxs-lookup"><span data-stu-id="109dd-320">Tables</span></span>  
  
-   <span data-ttu-id="109dd-321">Colonne</span><span class="sxs-lookup"><span data-stu-id="109dd-321">Columns</span></span>  
  
-   <span data-ttu-id="109dd-322">Procedure</span><span class="sxs-lookup"><span data-stu-id="109dd-322">Procedures</span></span>  
  
-   <span data-ttu-id="109dd-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="109dd-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="109dd-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="109dd-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="109dd-325">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="109dd-325">Views</span></span>  
  
-   <span data-ttu-id="109dd-326">Indexes</span><span class="sxs-lookup"><span data-stu-id="109dd-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="109dd-327">Tabelle</span><span class="sxs-lookup"><span data-stu-id="109dd-327">Tables</span></span>  
  
|<span data-ttu-id="109dd-328">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="109dd-328">ColumnName</span></span>|<span data-ttu-id="109dd-329">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="109dd-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="109dd-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="109dd-330">TABLE_CATALOG</span></span>|<span data-ttu-id="109dd-331">String</span><span class="sxs-lookup"><span data-stu-id="109dd-331">String</span></span>|  
|<span data-ttu-id="109dd-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="109dd-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="109dd-333">String</span><span class="sxs-lookup"><span data-stu-id="109dd-333">String</span></span>|  
|<span data-ttu-id="109dd-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-334">TABLE_NAME</span></span>|<span data-ttu-id="109dd-335">String</span><span class="sxs-lookup"><span data-stu-id="109dd-335">String</span></span>|  
|<span data-ttu-id="109dd-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="109dd-336">TABLE_TYPE</span></span>|<span data-ttu-id="109dd-337">String</span><span class="sxs-lookup"><span data-stu-id="109dd-337">String</span></span>|  
|<span data-ttu-id="109dd-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="109dd-338">TABLE_GUID</span></span>|<span data-ttu-id="109dd-339">Guid</span><span class="sxs-lookup"><span data-stu-id="109dd-339">Guid</span></span>|  
|<span data-ttu-id="109dd-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="109dd-340">DESCRIPTION</span></span>|<span data-ttu-id="109dd-341">String</span><span class="sxs-lookup"><span data-stu-id="109dd-341">String</span></span>|  
|<span data-ttu-id="109dd-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="109dd-342">TABLE_PROPID</span></span>|<span data-ttu-id="109dd-343">Int64</span><span class="sxs-lookup"><span data-stu-id="109dd-343">Int64</span></span>|  
|<span data-ttu-id="109dd-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="109dd-344">DATE_CREATED</span></span>|<span data-ttu-id="109dd-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="109dd-345">DateTime</span></span>|  
|<span data-ttu-id="109dd-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="109dd-346">DATE_MODIFIED</span></span>|<span data-ttu-id="109dd-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="109dd-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="109dd-348">Colonne</span><span class="sxs-lookup"><span data-stu-id="109dd-348">Columns</span></span>  
  
|<span data-ttu-id="109dd-349">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="109dd-349">ColumnName</span></span>|<span data-ttu-id="109dd-350">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="109dd-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="109dd-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="109dd-351">TABLE_CATALOG</span></span>|<span data-ttu-id="109dd-352">String</span><span class="sxs-lookup"><span data-stu-id="109dd-352">String</span></span>|  
|<span data-ttu-id="109dd-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="109dd-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="109dd-354">String</span><span class="sxs-lookup"><span data-stu-id="109dd-354">String</span></span>|  
|<span data-ttu-id="109dd-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-355">TABLE_NAME</span></span>|<span data-ttu-id="109dd-356">String</span><span class="sxs-lookup"><span data-stu-id="109dd-356">String</span></span>|  
|<span data-ttu-id="109dd-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-357">COLUMN_NAME</span></span>|<span data-ttu-id="109dd-358">String</span><span class="sxs-lookup"><span data-stu-id="109dd-358">String</span></span>|  
|<span data-ttu-id="109dd-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="109dd-359">COLUMN_GUID</span></span>|<span data-ttu-id="109dd-360">Guid</span><span class="sxs-lookup"><span data-stu-id="109dd-360">Guid</span></span>|  
|<span data-ttu-id="109dd-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="109dd-361">COLUMN_PROPID</span></span>|<span data-ttu-id="109dd-362">Int64</span><span class="sxs-lookup"><span data-stu-id="109dd-362">Int64</span></span>|  
|<span data-ttu-id="109dd-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="109dd-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="109dd-364">Int64</span><span class="sxs-lookup"><span data-stu-id="109dd-364">Int64</span></span>|  
|<span data-ttu-id="109dd-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="109dd-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="109dd-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="109dd-366">Boolean</span></span>|  
|<span data-ttu-id="109dd-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="109dd-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="109dd-368">String</span><span class="sxs-lookup"><span data-stu-id="109dd-368">String</span></span>|  
|<span data-ttu-id="109dd-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="109dd-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="109dd-370">Int64</span><span class="sxs-lookup"><span data-stu-id="109dd-370">Int64</span></span>|  
|<span data-ttu-id="109dd-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="109dd-371">IS_NULLABLE</span></span>|<span data-ttu-id="109dd-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="109dd-372">Boolean</span></span>|  
|<span data-ttu-id="109dd-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="109dd-373">DATA_TYPE</span></span>|<span data-ttu-id="109dd-374">Int32</span><span class="sxs-lookup"><span data-stu-id="109dd-374">Int32</span></span>|  
|<span data-ttu-id="109dd-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="109dd-375">TYPE_GUID</span></span>|<span data-ttu-id="109dd-376">Guid</span><span class="sxs-lookup"><span data-stu-id="109dd-376">Guid</span></span>|  
|<span data-ttu-id="109dd-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="109dd-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="109dd-378">Int64</span><span class="sxs-lookup"><span data-stu-id="109dd-378">Int64</span></span>|  
|<span data-ttu-id="109dd-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="109dd-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="109dd-380">Int64</span><span class="sxs-lookup"><span data-stu-id="109dd-380">Int64</span></span>|  
|<span data-ttu-id="109dd-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="109dd-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="109dd-382">Int32</span><span class="sxs-lookup"><span data-stu-id="109dd-382">Int32</span></span>|  
|<span data-ttu-id="109dd-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="109dd-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="109dd-384">Int16</span><span class="sxs-lookup"><span data-stu-id="109dd-384">Int16</span></span>|  
|<span data-ttu-id="109dd-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="109dd-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="109dd-386">Int64</span><span class="sxs-lookup"><span data-stu-id="109dd-386">Int64</span></span>|  
|<span data-ttu-id="109dd-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="109dd-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="109dd-388">String</span><span class="sxs-lookup"><span data-stu-id="109dd-388">String</span></span>|  
|<span data-ttu-id="109dd-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="109dd-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="109dd-390">String</span><span class="sxs-lookup"><span data-stu-id="109dd-390">String</span></span>|  
|<span data-ttu-id="109dd-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="109dd-392">String</span><span class="sxs-lookup"><span data-stu-id="109dd-392">String</span></span>|  
|<span data-ttu-id="109dd-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="109dd-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="109dd-394">String</span><span class="sxs-lookup"><span data-stu-id="109dd-394">String</span></span>|  
|<span data-ttu-id="109dd-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="109dd-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="109dd-396">String</span><span class="sxs-lookup"><span data-stu-id="109dd-396">String</span></span>|  
|<span data-ttu-id="109dd-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-397">COLLATION_NAME</span></span>|<span data-ttu-id="109dd-398">String</span><span class="sxs-lookup"><span data-stu-id="109dd-398">String</span></span>|  
|<span data-ttu-id="109dd-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="109dd-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="109dd-400">String</span><span class="sxs-lookup"><span data-stu-id="109dd-400">String</span></span>|  
|<span data-ttu-id="109dd-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="109dd-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="109dd-402">String</span><span class="sxs-lookup"><span data-stu-id="109dd-402">String</span></span>|  
|<span data-ttu-id="109dd-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-403">DOMAIN_NAME</span></span>|<span data-ttu-id="109dd-404">String</span><span class="sxs-lookup"><span data-stu-id="109dd-404">String</span></span>|  
|<span data-ttu-id="109dd-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="109dd-405">DESCRIPTION</span></span>|<span data-ttu-id="109dd-406">String</span><span class="sxs-lookup"><span data-stu-id="109dd-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="109dd-407">Procedure</span><span class="sxs-lookup"><span data-stu-id="109dd-407">Procedures</span></span>  
  
|<span data-ttu-id="109dd-408">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="109dd-408">ColumnName</span></span>|<span data-ttu-id="109dd-409">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="109dd-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="109dd-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="109dd-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="109dd-411">String</span><span class="sxs-lookup"><span data-stu-id="109dd-411">String</span></span>|  
|<span data-ttu-id="109dd-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="109dd-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="109dd-413">String</span><span class="sxs-lookup"><span data-stu-id="109dd-413">String</span></span>|  
|<span data-ttu-id="109dd-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="109dd-415">String</span><span class="sxs-lookup"><span data-stu-id="109dd-415">String</span></span>|  
|<span data-ttu-id="109dd-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="109dd-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="109dd-417">Int16</span><span class="sxs-lookup"><span data-stu-id="109dd-417">Int16</span></span>|  
|<span data-ttu-id="109dd-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="109dd-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="109dd-419">String</span><span class="sxs-lookup"><span data-stu-id="109dd-419">String</span></span>|  
|<span data-ttu-id="109dd-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="109dd-420">DESCRIPTION</span></span>|<span data-ttu-id="109dd-421">String</span><span class="sxs-lookup"><span data-stu-id="109dd-421">String</span></span>|  
|<span data-ttu-id="109dd-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="109dd-422">DATE_CREATED</span></span>|<span data-ttu-id="109dd-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="109dd-423">DateTime</span></span>|  
|<span data-ttu-id="109dd-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="109dd-424">DATE_MODIFIED</span></span>|<span data-ttu-id="109dd-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="109dd-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="109dd-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="109dd-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="109dd-427">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="109dd-427">ColumnName</span></span>|<span data-ttu-id="109dd-428">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="109dd-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="109dd-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="109dd-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="109dd-430">String</span><span class="sxs-lookup"><span data-stu-id="109dd-430">String</span></span>|  
|<span data-ttu-id="109dd-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="109dd-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="109dd-432">String</span><span class="sxs-lookup"><span data-stu-id="109dd-432">String</span></span>|  
|<span data-ttu-id="109dd-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="109dd-434">String</span><span class="sxs-lookup"><span data-stu-id="109dd-434">String</span></span>|  
|<span data-ttu-id="109dd-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-435">COLUMN_NAME</span></span>|<span data-ttu-id="109dd-436">String</span><span class="sxs-lookup"><span data-stu-id="109dd-436">String</span></span>|  
|<span data-ttu-id="109dd-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="109dd-437">COLUMN_GUID</span></span>|<span data-ttu-id="109dd-438">Guid</span><span class="sxs-lookup"><span data-stu-id="109dd-438">Guid</span></span>|  
|<span data-ttu-id="109dd-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="109dd-439">COLUMN_PROPID</span></span>|<span data-ttu-id="109dd-440">Int64</span><span class="sxs-lookup"><span data-stu-id="109dd-440">Int64</span></span>|  
|<span data-ttu-id="109dd-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="109dd-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="109dd-442">Int64</span><span class="sxs-lookup"><span data-stu-id="109dd-442">Int64</span></span>|  
|<span data-ttu-id="109dd-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="109dd-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="109dd-444">Int64</span><span class="sxs-lookup"><span data-stu-id="109dd-444">Int64</span></span>|  
|<span data-ttu-id="109dd-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="109dd-445">IS_NULLABLE</span></span>|<span data-ttu-id="109dd-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="109dd-446">Boolean</span></span>|  
|<span data-ttu-id="109dd-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="109dd-447">DATA_TYPE</span></span>|<span data-ttu-id="109dd-448">Int32</span><span class="sxs-lookup"><span data-stu-id="109dd-448">Int32</span></span>|  
|<span data-ttu-id="109dd-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="109dd-449">TYPE_GUID</span></span>|<span data-ttu-id="109dd-450">Guid</span><span class="sxs-lookup"><span data-stu-id="109dd-450">Guid</span></span>|  
|<span data-ttu-id="109dd-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="109dd-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="109dd-452">Int64</span><span class="sxs-lookup"><span data-stu-id="109dd-452">Int64</span></span>|  
|<span data-ttu-id="109dd-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="109dd-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="109dd-454">Int64</span><span class="sxs-lookup"><span data-stu-id="109dd-454">Int64</span></span>|  
|<span data-ttu-id="109dd-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="109dd-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="109dd-456">Int32</span><span class="sxs-lookup"><span data-stu-id="109dd-456">Int32</span></span>|  
|<span data-ttu-id="109dd-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="109dd-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="109dd-458">Int16</span><span class="sxs-lookup"><span data-stu-id="109dd-458">Int16</span></span>|  
|<span data-ttu-id="109dd-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="109dd-459">DESCRIPTION</span></span>|<span data-ttu-id="109dd-460">String</span><span class="sxs-lookup"><span data-stu-id="109dd-460">String</span></span>|  
|<span data-ttu-id="109dd-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="109dd-461">OVERLOAD</span></span>|<span data-ttu-id="109dd-462">Int16</span><span class="sxs-lookup"><span data-stu-id="109dd-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="109dd-463">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="109dd-463">Views</span></span>  
  
|<span data-ttu-id="109dd-464">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="109dd-464">ColumnName</span></span>|<span data-ttu-id="109dd-465">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="109dd-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="109dd-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="109dd-466">TABLE_CATALOG</span></span>|<span data-ttu-id="109dd-467">String</span><span class="sxs-lookup"><span data-stu-id="109dd-467">String</span></span>|  
|<span data-ttu-id="109dd-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="109dd-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="109dd-469">String</span><span class="sxs-lookup"><span data-stu-id="109dd-469">String</span></span>|  
|<span data-ttu-id="109dd-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-470">TABLE_NAME</span></span>|<span data-ttu-id="109dd-471">String</span><span class="sxs-lookup"><span data-stu-id="109dd-471">String</span></span>|  
|<span data-ttu-id="109dd-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="109dd-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="109dd-473">String</span><span class="sxs-lookup"><span data-stu-id="109dd-473">String</span></span>|  
|<span data-ttu-id="109dd-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="109dd-474">CHECK_OPTION</span></span>|<span data-ttu-id="109dd-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="109dd-475">Boolean</span></span>|  
|<span data-ttu-id="109dd-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="109dd-476">IS_UPDATABLE</span></span>|<span data-ttu-id="109dd-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="109dd-477">Boolean</span></span>|  
|<span data-ttu-id="109dd-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="109dd-478">DESCRIPTION</span></span>|<span data-ttu-id="109dd-479">String</span><span class="sxs-lookup"><span data-stu-id="109dd-479">String</span></span>|  
|<span data-ttu-id="109dd-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="109dd-480">DATE_CREATED</span></span>|<span data-ttu-id="109dd-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="109dd-481">DateTime</span></span>|  
|<span data-ttu-id="109dd-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="109dd-482">DATE_MODIFIED</span></span>|<span data-ttu-id="109dd-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="109dd-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="109dd-484">Indexes</span><span class="sxs-lookup"><span data-stu-id="109dd-484">Indexes</span></span>  
  
|<span data-ttu-id="109dd-485">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="109dd-485">ColumnName</span></span>|<span data-ttu-id="109dd-486">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="109dd-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="109dd-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="109dd-487">TABLE_CATALOG</span></span>|<span data-ttu-id="109dd-488">String</span><span class="sxs-lookup"><span data-stu-id="109dd-488">String</span></span>|  
|<span data-ttu-id="109dd-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="109dd-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="109dd-490">String</span><span class="sxs-lookup"><span data-stu-id="109dd-490">String</span></span>|  
|<span data-ttu-id="109dd-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-491">TABLE_NAME</span></span>|<span data-ttu-id="109dd-492">String</span><span class="sxs-lookup"><span data-stu-id="109dd-492">String</span></span>|  
|<span data-ttu-id="109dd-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="109dd-493">INDEX_CATALOG</span></span>|<span data-ttu-id="109dd-494">String</span><span class="sxs-lookup"><span data-stu-id="109dd-494">String</span></span>|  
|<span data-ttu-id="109dd-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="109dd-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="109dd-496">String</span><span class="sxs-lookup"><span data-stu-id="109dd-496">String</span></span>|  
|<span data-ttu-id="109dd-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-497">INDEX_NAME</span></span>|<span data-ttu-id="109dd-498">String</span><span class="sxs-lookup"><span data-stu-id="109dd-498">String</span></span>|  
|<span data-ttu-id="109dd-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="109dd-499">PRIMARY_KEY</span></span>|<span data-ttu-id="109dd-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="109dd-500">Boolean</span></span>|  
|<span data-ttu-id="109dd-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="109dd-501">UNIQUE</span></span>|<span data-ttu-id="109dd-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="109dd-502">Boolean</span></span>|  
|<span data-ttu-id="109dd-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="109dd-503">CLUSTERED</span></span>|<span data-ttu-id="109dd-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="109dd-504">Boolean</span></span>|  
|<span data-ttu-id="109dd-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="109dd-505">TYPE</span></span>|<span data-ttu-id="109dd-506">Int32</span><span class="sxs-lookup"><span data-stu-id="109dd-506">Int32</span></span>|  
|<span data-ttu-id="109dd-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="109dd-507">FILL_FACTOR</span></span>|<span data-ttu-id="109dd-508">Int32</span><span class="sxs-lookup"><span data-stu-id="109dd-508">Int32</span></span>|  
|<span data-ttu-id="109dd-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="109dd-509">INITIAL_SIZE</span></span>|<span data-ttu-id="109dd-510">Int32</span><span class="sxs-lookup"><span data-stu-id="109dd-510">Int32</span></span>|  
|<span data-ttu-id="109dd-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="109dd-511">NULLS</span></span>|<span data-ttu-id="109dd-512">Int32</span><span class="sxs-lookup"><span data-stu-id="109dd-512">Int32</span></span>|  
|<span data-ttu-id="109dd-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="109dd-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="109dd-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="109dd-514">Boolean</span></span>|  
|<span data-ttu-id="109dd-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="109dd-515">AUTO_UPDATE</span></span>|<span data-ttu-id="109dd-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="109dd-516">Boolean</span></span>|  
|<span data-ttu-id="109dd-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="109dd-517">NULL_COLLATION</span></span>|<span data-ttu-id="109dd-518">Int32</span><span class="sxs-lookup"><span data-stu-id="109dd-518">Int32</span></span>|  
|<span data-ttu-id="109dd-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="109dd-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="109dd-520">Int64</span><span class="sxs-lookup"><span data-stu-id="109dd-520">Int64</span></span>|  
|<span data-ttu-id="109dd-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-521">COLUMN_NAME</span></span>|<span data-ttu-id="109dd-522">String</span><span class="sxs-lookup"><span data-stu-id="109dd-522">String</span></span>|  
|<span data-ttu-id="109dd-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="109dd-523">COLUMN_GUID</span></span>|<span data-ttu-id="109dd-524">Guid</span><span class="sxs-lookup"><span data-stu-id="109dd-524">Guid</span></span>|  
|<span data-ttu-id="109dd-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="109dd-525">COLUMN_PROPID</span></span>|<span data-ttu-id="109dd-526">Int64</span><span class="sxs-lookup"><span data-stu-id="109dd-526">Int64</span></span>|  
|<span data-ttu-id="109dd-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="109dd-527">COLLATION</span></span>|<span data-ttu-id="109dd-528">Int16</span><span class="sxs-lookup"><span data-stu-id="109dd-528">Int16</span></span>|  
|<span data-ttu-id="109dd-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="109dd-529">CARDINALITY</span></span>|<span data-ttu-id="109dd-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="109dd-530">Decimal</span></span>|  
|<span data-ttu-id="109dd-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="109dd-531">PAGES</span></span>|<span data-ttu-id="109dd-532">Int32</span><span class="sxs-lookup"><span data-stu-id="109dd-532">Int32</span></span>|  
|<span data-ttu-id="109dd-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="109dd-533">FILTER_CONDITION</span></span>|<span data-ttu-id="109dd-534">String</span><span class="sxs-lookup"><span data-stu-id="109dd-534">String</span></span>|  
|<span data-ttu-id="109dd-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="109dd-535">INTEGRATED</span></span>|<span data-ttu-id="109dd-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="109dd-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="109dd-537">Provider OLE DB per Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="109dd-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="109dd-538">Oltre alle raccolte di schemi comuni, il driver OLE DB di Microsoft Jet supporta le raccolte di schemi specifici seguenti:</span><span class="sxs-lookup"><span data-stu-id="109dd-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="109dd-539">Tabelle</span><span class="sxs-lookup"><span data-stu-id="109dd-539">Tables</span></span>  
  
-   <span data-ttu-id="109dd-540">Colonne</span><span class="sxs-lookup"><span data-stu-id="109dd-540">Columns</span></span>  
  
-   <span data-ttu-id="109dd-541">Procedure</span><span class="sxs-lookup"><span data-stu-id="109dd-541">Procedures</span></span>  
  
-   <span data-ttu-id="109dd-542">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="109dd-542">Views</span></span>  
  
-   <span data-ttu-id="109dd-543">Indexes</span><span class="sxs-lookup"><span data-stu-id="109dd-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="109dd-544">Tabelle</span><span class="sxs-lookup"><span data-stu-id="109dd-544">Tables</span></span>  
  
|<span data-ttu-id="109dd-545">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="109dd-545">ColumnName</span></span>|<span data-ttu-id="109dd-546">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="109dd-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="109dd-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="109dd-547">TABLE_CATALOG</span></span>|<span data-ttu-id="109dd-548">String</span><span class="sxs-lookup"><span data-stu-id="109dd-548">String</span></span>|  
|<span data-ttu-id="109dd-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="109dd-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="109dd-550">String</span><span class="sxs-lookup"><span data-stu-id="109dd-550">String</span></span>|  
|<span data-ttu-id="109dd-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-551">TABLE_NAME</span></span>|<span data-ttu-id="109dd-552">String</span><span class="sxs-lookup"><span data-stu-id="109dd-552">String</span></span>|  
|<span data-ttu-id="109dd-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="109dd-553">TABLE_TYPE</span></span>|<span data-ttu-id="109dd-554">String</span><span class="sxs-lookup"><span data-stu-id="109dd-554">String</span></span>|  
|<span data-ttu-id="109dd-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="109dd-555">TABLE_GUID</span></span>|<span data-ttu-id="109dd-556">Guid</span><span class="sxs-lookup"><span data-stu-id="109dd-556">Guid</span></span>|  
|<span data-ttu-id="109dd-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="109dd-557">DESCRIPTION</span></span>|<span data-ttu-id="109dd-558">String</span><span class="sxs-lookup"><span data-stu-id="109dd-558">String</span></span>|  
|<span data-ttu-id="109dd-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="109dd-559">TABLE_PROPID</span></span>|<span data-ttu-id="109dd-560">Int64</span><span class="sxs-lookup"><span data-stu-id="109dd-560">Int64</span></span>|  
|<span data-ttu-id="109dd-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="109dd-561">DATE_CREATED</span></span>|<span data-ttu-id="109dd-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="109dd-562">DateTime</span></span>|  
|<span data-ttu-id="109dd-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="109dd-563">DATE_MODIFIED</span></span>|<span data-ttu-id="109dd-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="109dd-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="109dd-565">Colonne</span><span class="sxs-lookup"><span data-stu-id="109dd-565">Columns</span></span>  
  
|<span data-ttu-id="109dd-566">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="109dd-566">ColumnName</span></span>|<span data-ttu-id="109dd-567">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="109dd-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="109dd-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="109dd-568">TABLE_CATALOG</span></span>|<span data-ttu-id="109dd-569">String</span><span class="sxs-lookup"><span data-stu-id="109dd-569">String</span></span>|  
|<span data-ttu-id="109dd-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="109dd-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="109dd-571">String</span><span class="sxs-lookup"><span data-stu-id="109dd-571">String</span></span>|  
|<span data-ttu-id="109dd-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-572">TABLE_NAME</span></span>|<span data-ttu-id="109dd-573">String</span><span class="sxs-lookup"><span data-stu-id="109dd-573">String</span></span>|  
|<span data-ttu-id="109dd-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-574">COLUMN_NAME</span></span>|<span data-ttu-id="109dd-575">String</span><span class="sxs-lookup"><span data-stu-id="109dd-575">String</span></span>|  
|<span data-ttu-id="109dd-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="109dd-576">COLUMN_GUID</span></span>|<span data-ttu-id="109dd-577">Guid</span><span class="sxs-lookup"><span data-stu-id="109dd-577">Guid</span></span>|  
|<span data-ttu-id="109dd-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="109dd-578">COLUMN_PROPID</span></span>|<span data-ttu-id="109dd-579">Int64</span><span class="sxs-lookup"><span data-stu-id="109dd-579">Int64</span></span>|  
|<span data-ttu-id="109dd-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="109dd-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="109dd-581">Int64</span><span class="sxs-lookup"><span data-stu-id="109dd-581">Int64</span></span>|  
|<span data-ttu-id="109dd-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="109dd-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="109dd-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="109dd-583">Boolean</span></span>|  
|<span data-ttu-id="109dd-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="109dd-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="109dd-585">String</span><span class="sxs-lookup"><span data-stu-id="109dd-585">String</span></span>|  
|<span data-ttu-id="109dd-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="109dd-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="109dd-587">Int64</span><span class="sxs-lookup"><span data-stu-id="109dd-587">Int64</span></span>|  
|<span data-ttu-id="109dd-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="109dd-588">IS_NULLABLE</span></span>|<span data-ttu-id="109dd-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="109dd-589">Boolean</span></span>|  
|<span data-ttu-id="109dd-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="109dd-590">DATA_TYPE</span></span>|<span data-ttu-id="109dd-591">Int32</span><span class="sxs-lookup"><span data-stu-id="109dd-591">Int32</span></span>|  
|<span data-ttu-id="109dd-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="109dd-592">TYPE_GUID</span></span>|<span data-ttu-id="109dd-593">Guid</span><span class="sxs-lookup"><span data-stu-id="109dd-593">Guid</span></span>|  
|<span data-ttu-id="109dd-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="109dd-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="109dd-595">Int64</span><span class="sxs-lookup"><span data-stu-id="109dd-595">Int64</span></span>|  
|<span data-ttu-id="109dd-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="109dd-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="109dd-597">Int64</span><span class="sxs-lookup"><span data-stu-id="109dd-597">Int64</span></span>|  
|<span data-ttu-id="109dd-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="109dd-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="109dd-599">Int32</span><span class="sxs-lookup"><span data-stu-id="109dd-599">Int32</span></span>|  
|<span data-ttu-id="109dd-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="109dd-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="109dd-601">Int16</span><span class="sxs-lookup"><span data-stu-id="109dd-601">Int16</span></span>|  
|<span data-ttu-id="109dd-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="109dd-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="109dd-603">Int64</span><span class="sxs-lookup"><span data-stu-id="109dd-603">Int64</span></span>|  
|<span data-ttu-id="109dd-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="109dd-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="109dd-605">String</span><span class="sxs-lookup"><span data-stu-id="109dd-605">String</span></span>|  
|<span data-ttu-id="109dd-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="109dd-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="109dd-607">String</span><span class="sxs-lookup"><span data-stu-id="109dd-607">String</span></span>|  
|<span data-ttu-id="109dd-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="109dd-609">String</span><span class="sxs-lookup"><span data-stu-id="109dd-609">String</span></span>|  
|<span data-ttu-id="109dd-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="109dd-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="109dd-611">String</span><span class="sxs-lookup"><span data-stu-id="109dd-611">String</span></span>|  
|<span data-ttu-id="109dd-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="109dd-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="109dd-613">String</span><span class="sxs-lookup"><span data-stu-id="109dd-613">String</span></span>|  
|<span data-ttu-id="109dd-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-614">COLLATION_NAME</span></span>|<span data-ttu-id="109dd-615">String</span><span class="sxs-lookup"><span data-stu-id="109dd-615">String</span></span>|  
|<span data-ttu-id="109dd-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="109dd-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="109dd-617">String</span><span class="sxs-lookup"><span data-stu-id="109dd-617">String</span></span>|  
|<span data-ttu-id="109dd-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="109dd-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="109dd-619">String</span><span class="sxs-lookup"><span data-stu-id="109dd-619">String</span></span>|  
|<span data-ttu-id="109dd-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-620">DOMAIN_NAME</span></span>|<span data-ttu-id="109dd-621">String</span><span class="sxs-lookup"><span data-stu-id="109dd-621">String</span></span>|  
|<span data-ttu-id="109dd-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="109dd-622">DESCRIPTION</span></span>|<span data-ttu-id="109dd-623">String</span><span class="sxs-lookup"><span data-stu-id="109dd-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="109dd-624">Procedure</span><span class="sxs-lookup"><span data-stu-id="109dd-624">Procedures</span></span>  
  
|<span data-ttu-id="109dd-625">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="109dd-625">ColumnName</span></span>|<span data-ttu-id="109dd-626">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="109dd-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="109dd-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="109dd-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="109dd-628">String</span><span class="sxs-lookup"><span data-stu-id="109dd-628">String</span></span>|  
|<span data-ttu-id="109dd-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="109dd-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="109dd-630">String</span><span class="sxs-lookup"><span data-stu-id="109dd-630">String</span></span>|  
|<span data-ttu-id="109dd-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="109dd-632">String</span><span class="sxs-lookup"><span data-stu-id="109dd-632">String</span></span>|  
|<span data-ttu-id="109dd-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="109dd-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="109dd-634">Int16</span><span class="sxs-lookup"><span data-stu-id="109dd-634">Int16</span></span>|  
|<span data-ttu-id="109dd-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="109dd-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="109dd-636">String</span><span class="sxs-lookup"><span data-stu-id="109dd-636">String</span></span>|  
|<span data-ttu-id="109dd-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="109dd-637">DESCRIPTION</span></span>|<span data-ttu-id="109dd-638">String</span><span class="sxs-lookup"><span data-stu-id="109dd-638">String</span></span>|  
|<span data-ttu-id="109dd-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="109dd-639">DATE_CREATED</span></span>|<span data-ttu-id="109dd-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="109dd-640">DateTime</span></span>|  
|<span data-ttu-id="109dd-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="109dd-641">DATE_MODIFIED</span></span>|<span data-ttu-id="109dd-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="109dd-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="109dd-643">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="109dd-643">Views</span></span>  
  
|<span data-ttu-id="109dd-644">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="109dd-644">ColumnName</span></span>|<span data-ttu-id="109dd-645">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="109dd-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="109dd-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="109dd-646">TABLE_CATALOG</span></span>|<span data-ttu-id="109dd-647">String</span><span class="sxs-lookup"><span data-stu-id="109dd-647">String</span></span>|  
|<span data-ttu-id="109dd-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="109dd-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="109dd-649">String</span><span class="sxs-lookup"><span data-stu-id="109dd-649">String</span></span>|  
|<span data-ttu-id="109dd-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-650">TABLE_NAME</span></span>|<span data-ttu-id="109dd-651">String</span><span class="sxs-lookup"><span data-stu-id="109dd-651">String</span></span>|  
|<span data-ttu-id="109dd-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="109dd-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="109dd-653">String</span><span class="sxs-lookup"><span data-stu-id="109dd-653">String</span></span>|  
|<span data-ttu-id="109dd-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="109dd-654">CHECK_OPTION</span></span>|<span data-ttu-id="109dd-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="109dd-655">Boolean</span></span>|  
|<span data-ttu-id="109dd-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="109dd-656">IS_UPDATABLE</span></span>|<span data-ttu-id="109dd-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="109dd-657">Boolean</span></span>|  
|<span data-ttu-id="109dd-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="109dd-658">DESCRIPTION</span></span>|<span data-ttu-id="109dd-659">String</span><span class="sxs-lookup"><span data-stu-id="109dd-659">String</span></span>|  
|<span data-ttu-id="109dd-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="109dd-660">DATE_CREATED</span></span>|<span data-ttu-id="109dd-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="109dd-661">DateTime</span></span>|  
|<span data-ttu-id="109dd-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="109dd-662">DATE_MODIFIED</span></span>|<span data-ttu-id="109dd-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="109dd-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="109dd-664">Indexes</span><span class="sxs-lookup"><span data-stu-id="109dd-664">Indexes</span></span>  
  
|<span data-ttu-id="109dd-665">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="109dd-665">ColumnName</span></span>|<span data-ttu-id="109dd-666">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="109dd-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="109dd-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="109dd-667">TABLE_CATALOG</span></span>|<span data-ttu-id="109dd-668">String</span><span class="sxs-lookup"><span data-stu-id="109dd-668">String</span></span>|  
|<span data-ttu-id="109dd-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="109dd-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="109dd-670">String</span><span class="sxs-lookup"><span data-stu-id="109dd-670">String</span></span>|  
|<span data-ttu-id="109dd-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-671">TABLE_NAME</span></span>|<span data-ttu-id="109dd-672">String</span><span class="sxs-lookup"><span data-stu-id="109dd-672">String</span></span>|  
|<span data-ttu-id="109dd-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="109dd-673">INDEX_CATALOG</span></span>|<span data-ttu-id="109dd-674">String</span><span class="sxs-lookup"><span data-stu-id="109dd-674">String</span></span>|  
|<span data-ttu-id="109dd-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="109dd-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="109dd-676">String</span><span class="sxs-lookup"><span data-stu-id="109dd-676">String</span></span>|  
|<span data-ttu-id="109dd-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-677">INDEX_NAME</span></span>|<span data-ttu-id="109dd-678">String</span><span class="sxs-lookup"><span data-stu-id="109dd-678">String</span></span>|  
|<span data-ttu-id="109dd-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="109dd-679">PRIMARY_KEY</span></span>|<span data-ttu-id="109dd-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="109dd-680">Boolean</span></span>|  
|<span data-ttu-id="109dd-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="109dd-681">UNIQUE</span></span>|<span data-ttu-id="109dd-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="109dd-682">Boolean</span></span>|  
|<span data-ttu-id="109dd-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="109dd-683">CLUSTERED</span></span>|<span data-ttu-id="109dd-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="109dd-684">Boolean</span></span>|  
|<span data-ttu-id="109dd-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="109dd-685">TYPE</span></span>|<span data-ttu-id="109dd-686">Int32</span><span class="sxs-lookup"><span data-stu-id="109dd-686">Int32</span></span>|  
|<span data-ttu-id="109dd-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="109dd-687">FILL_FACTOR</span></span>|<span data-ttu-id="109dd-688">Int32</span><span class="sxs-lookup"><span data-stu-id="109dd-688">Int32</span></span>|  
|<span data-ttu-id="109dd-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="109dd-689">INITIAL_SIZE</span></span>|<span data-ttu-id="109dd-690">Int32</span><span class="sxs-lookup"><span data-stu-id="109dd-690">Int32</span></span>|  
|<span data-ttu-id="109dd-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="109dd-691">NULLS</span></span>|<span data-ttu-id="109dd-692">Int32</span><span class="sxs-lookup"><span data-stu-id="109dd-692">Int32</span></span>|  
|<span data-ttu-id="109dd-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="109dd-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="109dd-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="109dd-694">Boolean</span></span>|  
|<span data-ttu-id="109dd-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="109dd-695">AUTO_UPDATE</span></span>|<span data-ttu-id="109dd-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="109dd-696">Boolean</span></span>|  
|<span data-ttu-id="109dd-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="109dd-697">NULL_COLLATION</span></span>|<span data-ttu-id="109dd-698">Int32</span><span class="sxs-lookup"><span data-stu-id="109dd-698">Int32</span></span>|  
|<span data-ttu-id="109dd-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="109dd-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="109dd-700">Int64</span><span class="sxs-lookup"><span data-stu-id="109dd-700">Int64</span></span>|  
|<span data-ttu-id="109dd-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="109dd-701">COLUMN_NAME</span></span>|<span data-ttu-id="109dd-702">String</span><span class="sxs-lookup"><span data-stu-id="109dd-702">String</span></span>|  
|<span data-ttu-id="109dd-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="109dd-703">COLUMN_GUID</span></span>|<span data-ttu-id="109dd-704">Guid</span><span class="sxs-lookup"><span data-stu-id="109dd-704">Guid</span></span>|  
|<span data-ttu-id="109dd-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="109dd-705">COLUMN_PROPID</span></span>|<span data-ttu-id="109dd-706">Int64</span><span class="sxs-lookup"><span data-stu-id="109dd-706">Int64</span></span>|  
|<span data-ttu-id="109dd-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="109dd-707">COLLATION</span></span>|<span data-ttu-id="109dd-708">Int16</span><span class="sxs-lookup"><span data-stu-id="109dd-708">Int16</span></span>|  
|<span data-ttu-id="109dd-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="109dd-709">CARDINALITY</span></span>|<span data-ttu-id="109dd-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="109dd-710">Decimal</span></span>|  
|<span data-ttu-id="109dd-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="109dd-711">PAGES</span></span>|<span data-ttu-id="109dd-712">Int32</span><span class="sxs-lookup"><span data-stu-id="109dd-712">Int32</span></span>|  
|<span data-ttu-id="109dd-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="109dd-713">FILTER_CONDITION</span></span>|<span data-ttu-id="109dd-714">String</span><span class="sxs-lookup"><span data-stu-id="109dd-714">String</span></span>|  
|<span data-ttu-id="109dd-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="109dd-715">INTEGRATED</span></span>|<span data-ttu-id="109dd-716">Booleano</span><span class="sxs-lookup"><span data-stu-id="109dd-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="109dd-717">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="109dd-717">See Also</span></span>  
 [<span data-ttu-id="109dd-718">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="109dd-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
