project.name = "Katana"

# Katana Framework target
katana = target do |target|
    target.name = "Katana"
    target.platform = :ios
    target.deployment_target = 11.0
    target.language = :swift
    target.type = :framework
    target.include_files = [
        "Katana/**/*.swift",
    ]

    target.all_configurations.each do |configuration|
        configuration.settings["INFOPLIST_FILE"] = "Katana/Info.plist"
        configuration.settings["PRODUCT_NAME"] = "Katana"
    end

    target.headers_build_phase do |phase|
        phase.public << "Katana/Katana.h"
    end

    unit_tests_for target do |unit_test|
        unit_test.linked_targets = [target]
        unit_test.include_files = [
            "KatanaTests/**/*.swift",
        ]

        unit_test.all_configurations.each do |configuration|
            configuration.settings["INFOPLIST_FILE"] = "KatanaTests/Info.plist"
        end
    end

    target.scheme(target.name)
end
