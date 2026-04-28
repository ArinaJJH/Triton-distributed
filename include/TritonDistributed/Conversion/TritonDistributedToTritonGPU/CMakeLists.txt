if(TRITON_USE_MACA)
  set(PASSES_TD Passes_maca.td)
else()
  set(PASSES_TD Passes.td)
endif()

set(LLVM_TARGET_DEFINITIONS ${PASSES_TD})
mlir_tablegen(Passes.h.inc -gen-pass-decls --name TritonDistributedToTritonGPU)
add_public_tablegen_target(TritonDistributedConversionPassIncGen)
