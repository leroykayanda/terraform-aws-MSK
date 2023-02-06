This is a terraform module to set up an amazon MSK / apache kafka cluster.

    module "amazon_msk_cluster" {
      source                      = "leroykayanda/MSK/aws"
      version                     = "1.0.1"
      microservice_name           = var.microservice_name
      env                         = var.env
      team                        = var.team
      kafka_client_subnets        = var.kafka_client_subnets
      broker_ebs_volume_size      = var.broker_ebs_volume_size
      broker_instance_type        = var.broker_instance_type
      kafka_version               = var.kafka_version
      number_of_broker_nodes      = var.number_of_broker_nodes
      kafka_enhanced_monitoring   = var.kafka_enhanced_monitoring
      kafka_logs_retention_period = var.kafka_logs_retention_period
      security_group_id           = aws_security_group.kafka_sg.id
      public_access               = var.kafka_public_access
    }
