python_lib(starknet_testing_lib
    PREFIX starkware/starknet/testing

    FILES
    contract.py
    starknet.py

    LIBS
    cairo_vm_crypto_lib
    starknet_abi_lib
    starknet_business_logic_lib
    starknet_compile_lib
    starknet_contract_definition_lib
    starknet_definitions_lib
    starknet_general_config_lib
    starknet_internal_transaction_interface_lib
    starknet_internal_transaction_lib
    starkware_storage_lib
)

full_python_test(starknet_testing_test
    PREFIX starkware/starknet/testing
    PYTHON python3.7
    TESTED_MODULES starkware/starknet/testing

    FILES
    contract_test.py
    starknet_test.py
    test.cairo

    LIBS
    starknet_testing_lib
    pip_pytest
    pip_pytest_asyncio
)
