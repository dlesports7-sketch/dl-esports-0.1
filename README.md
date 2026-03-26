# List of rules
GENERATED_RULES = %i[
  xcode_file?
  intellij_file?
  cocoapods?
  carthage_build?
  generated_graphql_relay?
  node_modules?
  minified_files?
  source_map?
].freeze

def generated?
  GENERATED_RULES.any? do |rule|
    respond_to?(rule, true) && public_send(rule)
  end
end
